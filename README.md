# The function error and solve


(1) 统计描述
运行代码：
senstest <- get_statistics(data = sens,
                        Group = "indexx",
                        variables = colnames(sens)[c(5)],
                        diff_test = T,
                        docx_file = "Table1_插补前后敏感性分析结果.docx")
Error: 其中第五列为连续性变量。                        
Error in `[.data.frame`(norrom, 8) : 选择了未定义的列

Solution：
修改function中的：
# skew <- norrom[8]#偏度   ————————>  skew <- norrom[8,]#偏度 
# kurtosis <- norrom[10]#峰度  ————————>  kurtosis <- norrom[10,]#峰度
