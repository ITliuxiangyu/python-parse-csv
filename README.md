# python-parse-csv
# python 解析csv文件

# -*- coding:utf8 -*-  

import csv
import os
import pymysql
import pandas as pd

def readCsvIntoDb():
    try:
        with open('user.csv' , encoding="gbk") as f:
            data = pd.read_csv(f)
            for i in range(len(data["name"])):
                username = data["name"][i]
                age = data["age"][i]
                userId = str(data["userid"][i])

                conn = pymysql.(host = "******" , port = 3306 , user = "root" , password = "12345678" , database = "yyy" , charset = "utf8")
                cursor=conn.cursor() 
                sqlStr = 'INSERT INTO chenyunfei (username,age,userid) VALUES ("%s","%s","%s")' % (username , age , userId)
                cursor.execute(sqlStr)
                conn.commit()
                conn.close()
            print("添加信息成功")
    except Exception as e:
            print("添加信息失败")
readCsvIntoDb()
