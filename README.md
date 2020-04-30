# 中文版本Python_picos（求解器CPLEX）教程
====
自己进行安装、优化、求解的过程中发现这方面的中文教程很少，现做记录，如有缺漏失误，请随时提醒我。
原文档地址：https://picos-api.gitlab.io/picos/introduction.html#installation



## 目录

### 第一章：Picos入门

1. [Picos 简介](chapter1/1.1-Picos-introduction.md)
2. [Picos 安装](chapter1/1.2-Picos-installation.md)

# 1.简介

picos是一个用于优化求解的Python API，适用于多个求解器，支持Python 2.x和3.x各版本。
常用底层求解器包括CPLEX、CVXOPT、ECOS、GLPK、Gurobi、MOSEK、SCIP以及SMCP。
CPLEX是IBM推出的底层优化器，分为社区版和学术版，社区版可以在官网下载，适用于数据较少的情况。学术版则需要使用学校邮箱进行申请，可免费使用。


# 2.安装

## picos
pip install picos或者
conda install -c picos picos

## CPLEX
### win
安装windows版本之后，从CPLEX的安装目录中寻找Python对应版本，将最内层CPLEX文件夹复制到对应site_packages文件夹中

打开jupyter
```
import picos
import cplex
p = picos.Problem()
x = picos.IntegerVariable("x",2)
p.add_constraint(x <= 5.5)
p.set_objective("max", picos.sum(x))
p.solve(solver="cplex")
p.value
print(x)
```
安装成功
