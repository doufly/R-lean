# R-lean
R语言学习

test<-read.table('C:\\Users\\dou\\Desktop\\新建文本文档.txt',header=T)
head(test)
class(test$name)
get.location<-function(h){
  split.location<-tryCatch(strsplit(as.character(h),',')[[1]],error= function(e) return(c(NA,NA)))
  clean.location<-gsub('^ ','',split.location)
  if (length(clean.location)!=2){
    return(c(NA,NA))
  }
  else{
    return(clean.location)
  }
}
get.location(test$name)
lapply(test$name,get.location)

split.location<-tryCatch(strsplit(test$name,',')[[1]],error= function(e) return(c(NA,NA)))
clean.location<-gsub('^ ','',split.location)
