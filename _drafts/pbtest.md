library(pbapply)
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
s <- 0.01
x1 <- lapply(n, f, s=s)
m1 <- t(sapply(x1, function(z) z["elapsed",] - z["expected",]))
x2 <- lapply(n, f, s=s)
m2 <- t(sapply(x2, function(z) z["elapsed",] - z["expected",]))
x3 <- lapply(n, f, s=s)
m3 <- t(sapply(x3, function(z) z["elapsed",] - z["expected",]))

m <- (m1+m2+m3)/3

op <- par(mfrow=c(1,2))
matplot(n, m, type="l", lty=1, lwd=3,
    ylab="Overhead (sec)", xlab="# iterations")
#matlines(n, m1, lty=1, type="l")
#matlines(n, m2, lty=1, type="l")
#matlines(n, m3, lty=1, type="l")
legend("topleft", bty="n", col=1:4, lwd=3, text.col=1:4,
    legend=colnames(m))
matplot(n, m/n, type="l", lty=1, lwd=3,
    ylab="Overhead / # iterations (sec)", xlab="# iterations")
#matlines(n, m1/n, lty=1, type="l")
#matlines(n, m2/n, lty=1, type="l")
#matlines(n, m3/n, lty=1, type="l")
par(op)


