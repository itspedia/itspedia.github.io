# 数据仓库之人物篇

数据仓库领域，在业界有几位公认大牛，

## 第一位 William H. (Bill) Inmon，

数据仓库之父，开山鼻祖，著书立说，培训演讲，出版了许多书，详见[wiki](https://en.wikipedia.org/wiki/Bill_Inmon#Publications) 我在这里推荐Building the Data Warehouse这本书，第**四**版出版于2005。他推崇使用Corporate Information Factory（CIF）的数据建模方法（使用范式模型构建企业数据仓库+各维度模型构建的业务主题数据集市），最近在新的数据仓库架构和实施方面和后起之秀Dan Linstedt合作推动新的搭建数据仓库的方法论 Data Vault

## 第二位 Ralph Kimball

使用维度模型构建数据仓库的开创者（Dimensional Data Warehouse）。他起初在一段不短的时间内就这个构建数据仓库方法论和Inmon的CIF展开激烈论战，最终他的方法论获得业界广泛认可，成为业界构建数据仓库的事实标准。他的书专注于实际实现考虑，以toolkit主题的有三本，

- The Data Warehouse Toolkit
- The Data Warehouse ETL Toolkit
- The Data Warehouse Lifecycle Toolkit

这三本书涵盖架构设计，模型设计，项目管理等多个主题，成为业界从业人员之必读。 这里不得不提[Chris Adamson](http://chrisadamson.com/)，业界资深顾问，一个Ralph Kimball方法论的追随者，著有Star Schema The Complete Reference等。

## 第三位 Dan Linstedt

创新性地提出使用Data Vault建模方法来设计数据仓库模型，后续推出Data Vault 2.0构建数据仓库方法论，涵盖建模、项目管理、架构和实现等方面，通过成立商业联盟和认证培训等商业手段积极推广。