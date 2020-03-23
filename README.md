--- 
title: "Problems and solutions"
author: "Xiaofang-Feng"
output: pdf_document 
---

#The compilation steps are as follows:

```{r eval=FALSE}

setwd("C:/Users/Administrator/Desktop/git/adv-r-master")

install.packages("bookdown")

install.packages("rmarkdown")

bookdown::render_book("index.Rmd", output_format="bookdown::pdf_book", encoding="UTF-8")

```


##error in Introduction.Rmd

Quitting from lines 223-235 (Introduction.Rmd) 
Error in cat(paste0(contributors$desc, collapse = ", ")) : 
  invalid multibyte string at '<86>,<4e>A (\@kfeng123), Karl Forner (\@kforner), Kirill Sevastyanenko (\@kirillseva), Brian Knaus (\@knausb), Kirill M眉ller (\@krlmlr), Kriti Sen Sharma (\@ksens), Kai Tang (鍞愭伜锛<89>,NA (\@ktang), Kevin Wright (\@kwstat), suo.lawrence.liu@gmail.com (\@Lawrence-Liu), \@ldfmrails, Kevin Kainan Li (\@legendre6891), Rachel Severson (\@leighseverson), Laurent Gatto (\@lgatto), C. Jason Liang (\@liangcj), Steve Lianoglou (\@lianos), Yongfu Liao (\@liao961120), Likan (\@likanzhan), \@lindbrook, Lingbing Feng (\@Lingbing), Marcel Ramos (\@LiNk-NY), Zhongpeng Lin (\@linzhp), Lionel Henry (\@lionel-), Llu铆s (\@llrs), myq (\@lrcg), Luke W Johnston (\@lwjohnst86), Kevin Lynagh (\@lynaghk), \@MajoroMask, Malcolm Barrett (\@malcolmbarrett), \@mannyishere, \@mascaretti, Matt (\@mattbaggott), Matthew Grogan (\@mattgrogan), \@matthewhillary, Matthieu Gomez (\@matthieugomez), Matt Malin (\@mattmalin), Mauro Lepore (\@maurolepore), Max Ghenis (\@MaxGhenis), M
Calls: local ... withCallingHandlers -> withVisible -> eval -> eval -> cat

Adding encoding = "UTF-8" in line 224 can fix it.
```{r eval=FALSE}
contributors <- read.csv("contributors.csv", stringsAsFactors = FALSE, encoding = "UTF-8")
```

##error in no package with the name 'emo':

Quitting from lines 96-103 (Functionals.Rmd) 
Error in loadNamespace(name) : 不存在叫'emo'这个名字的程辑包
Calls: local ... loadNamespace -> withRestarts -> withOneRestart -> doWithOneRestart

*Using
```{r eval=FALSE}
devtools::install_github("hadley/emo")#The following error occurs again
```

Downloading GitHub repo hadley/emo@master
Error in utils::download.file(url, path, method = method, quiet = quiet,  : 
  无法打开URL'https://api.github.com/repos/hadley/emo/tarball/master'

*Input $ git config --global http.sslBackend "openssl", $ git config --global http.sslCAInfo C:/Users/Administrator/Desktop/git/adv-r-master in gitbash
Then 
```{r eval=FALSE} 
devtools::install_github("hadley/sloop",force = TRUE), 
devtools::install_github("hadley/emo")
```

##Missing packages
I installed the following packages, named desc, sessioninfo,lobstr,testthat,emo,tibble, sloop,DBI,RSQLite,dbplyr,profvis,bench and ggbeeswarm. 
Most of them can be installed by install.packages(), but emo can not. 

##'make' not found
I add Rtools to the system path, and restart the step.

##'xelatex' not found
I installed the package named TinyTex first, but it failed. Then I successfully solved this problem by using MiKTeX. 

##Fonts
The font "Inconsolata" and "Andale Mono" cannot be found
Install the Inconsolata font and Andale Mono font, the problem is resolved by rerunning the code.
