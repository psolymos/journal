library(plyr)
## from http://ryouready.wordpress.com/2010/01/11/progress-bars-in-r-part-ii-a-wrapper-for-apply-functions/#comment-122
lapply_pb <-
function(X, FUN, ...)
{
    env <- environment()
    pb_Total <- length(X)
    counter <- 0
    pb <- txtProgressBar(min = 0, max = pb_Total, style = 3)
    wrapper <- function(...){
        curVal <- get("counter", envir = env)
        assign("counter", curVal +1 ,envir = env)
        setTxtProgressBar(get("pb", envir = env), curVal + 1)
        FUN(...)
    }
    res <- lapply(X, wrapper, ...)
    close(pb)
    res
}


f <- function(n, s=0.1) {
    i <- seq_len(n)
    t1 <- system.time(lapply(i, function(i) Sys.sleep(s)))
    t2 <- system.time(lapply_pb(i, function(i) Sys.sleep(s)))
    t3 <- system.time(l_ply(i, function(i) Sys.sleep(s), .progress="text"))
    t4 <- system.time(pblapply(i, function(i) Sys.sleep(s)))
    rbind(cbind(lapply=t1, lapply_pb=t2, l_ply=t3, pbapply=t4), expected=n*s)
}

n <- c(10, 50, 100, 200, 500, 1000)
s <- 0.05
x <- lapply(n, f, s=s)
m <- t(sapply(x, function(z) z["elapsed",] - z["expected",]))


op <- par(mfrow=c(1,2))
matplot(n, m, type="b", lty=1, ylab="Overhead (sec)", xlab="# iterations")
legend("topleft", bty="n", col=1:4, pch=as.character(1:4), text.col=1:4,
    legend=colnames(m))
matplot(n, m/n, type="b", lty=1, ylab="Overhead / # iterations (sec)", xlab="# iterations")
par(op)


