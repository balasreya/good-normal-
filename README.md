# good-normal
x<-c(3,5,7,9,11)
f<-c(1,4,6,4,1)
xi<-(x+y)/2
fx<-f*xi
fxx<-f*xi*xi
sumfx<-sum(f*xi)
print(sumfx)
sumfxx<-sum(f*xi*xi)
sumf<-sum(f)
print(sumf)
m<-sumfx/sumf
print(m)
sd<-(sumfxx/sumf)-(m*m)
sd<-sqrt(sd)
print(sd)
u<-pnorm(y,m,sd)
l<-pnorm(x,m,sd)
pr<-u-l
u<-round(u,digits=5)
l<-round(l,digits=5)
pr<-round(pr,digits=5)
fee<-(pr*sumf)
fe<-round(fee,digits=0)
mydata<- data.frame(x,y,xi,f,fx,fxx,u,l,pr,fee,fe)
print(mydata)
sums<-list(NA,NA,NA,sum(f),sum(f*xi),sum(f*xi*xi),NA,NA,NA,NA,sum(fe))
mydata<-rbind(mydata,sums)
print(mydata,row.names=FALSE)
result<-chisq.test(f,p=pr,rescale.p=TRUE)
print(result)



