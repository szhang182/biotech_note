Day 4,5,6 - 善 R note

Basics 

- 显示文件列表
    - dir()
    - list.files()
    - getwd()
- “ < - ” 赋值
    - a < - 5+6
- 删除变量
    - rm(a)
    - rm(list = ls())
- 历史命令
    - history()
- 清空控制台
    - ctrl+l

DS

- 向量（vector)
    - x<- c(1,2,3)
        - 123
    - x<- 1:10
        - 12345678910
    - x<- seq(1,10,by = 0.5)
        - 1 1.5 2 2.5….10
    - x<- rep(1:3,times=2)
        - 123123
    - x[4]
        - x第4个
    - x[-4]
        - 除了第4个元素
    - x[2:4]
        - 第2到4个元素
    - x[-(2:4)]
        - 除了第2-4个元素
    - x[c(1,5)]
        - 第1个和第5个元素
    - x[x==10]
    - x[x<0]
    - x[x %in% c(1,2,5)]
        - in c（1，2，5）
- 阵（Matrix）
- 数组（Array）
- 数据框（Data frame)
    - X<-read.csv('doudou.txt')
    - **read.table(file="huahua.txt",sep="\t",header=T)**
        - sep="\t": 指定字段之间的分隔符是tab
        - header=T: 这意味着文件的第一行是列名，因此应该被视为表头。T 是 TRUE
    - **a <- read.table(file="huahua.txt",sep="\t",header=T)**
    - colnames(X) 和 rownames(X)
    - colnames(X)[1]<-"bioplanet"
        - 修改数据框 **`X`** 的第一列的列名为 "bioplanet"
    - X<-read.csv(file = "huahua.txt",sep = "	",header =T,row.names=1)
        - 最后row.names的意思是修改第一列为行名
    - write.table(X,file = "yu.txt",sep = ",",quote=F)
        - **`quote=F`**: 这表示不为字符或因子列的值添加引号
        - 分隔符改为逗号，字符串不加双引号
    - save.image(file="bioinfoplanet.RData")
        - 保存当前所有变量
    - save(X,file="test.RData")
        - 保存其中一个变量
    - load("test.RData")
        - 再次使用RData时的加载命令
    - extract
        - X[x,y]
            - 第x行第y列
        - X[x,]
            - 第x行
        - X[,y]
            - 第y列
        - X[y]
            - 也是第y列
        - X[a:b]
            - 第a列到第b列
        - X[c(a,b)]
            - 第a列和第b列
        - X$列名
            - 也可以提取列
- List

R包

- install
    - install.packages(“包”)
    - BiocManager::install(“包”)
- Load
    - options("repos" = c(CRAN="[https://mirrors.tuna.tsinghua.edu.cn/CRAN/](https://mirrors.tuna.tsinghua.edu.cn/CRAN/)"))
    - options(BioC_mirror="[https://mirrors.ustc.edu.cn/bioc/](https://mirrors.ustc.edu.cn/bioc/)")
    - install.packages("dplyr")
    - library(dplyr)

5 basic functions

- mutate(test, new = Sepal.Length * Sepal.Width)
    - to add a new row
- select()
    - select by col number
        - select(test,1)
        - select(test,c(1,5))
    - select by col name
        - select(test, Petal.Length, Petal.Width)
        - vars <- c("Petal.Length", "Petal.Width")
        - select(test, one_of(vars))
- filter()
    - filter(test, Species == "setosa")
    - filter(test, Species == "setosa"&Sepal.Length>5)
    - filter(test, Species %in% c("setosa","versicolor"))
- arrange() 就是sort ascending by default
    - arrange(test, Sepal.Length)
    - arrange(test, desc(Sepal.Length))
- summarise()
    - summarise(test, mean(Sepal.Length), sd(Sepal.Length)
    - group_by(test, Species)
    - summarise(group_by(test, Species),mean(Sepal.Length), sd(Sepal.Length))
    

dplyr实用技能

- pipe  同linux pipe
    - test %>%
    - group_by(Species) %>%
    - summarise(mean(Sepal.Length), sd(Sepal.Length))
- count(test,Species)  count unique value

join or bind tables

- inner_join 同sql
    - inner_join(test1, test2, by = "x")
- left_join
    - left_join(test1, test2, by = 'x')
- full_join
    - full_join( test1, test2, by = 'x')
- semi_join 返回能够与y表匹配的x表所有记录
    - semi_join(x = test1, y = test2, by = 'x')
- anti_join 返回无法与y表匹配的x表的所记录
    - anti_join(x = test2, y = test1, by = 'x')
- bind_rows(test1, test2) 相当于append row
- bind_cols(test1, test3) 相当于 append col
