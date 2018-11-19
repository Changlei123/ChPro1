# ChPro1
# ChPro1 is my first project in Github!
# -*- coding: utf-8 -*-
"""
Created on Sun Nov 11 22:15:26 2018

@author: PC_GUO
"""

import psutil
import os,datetime,time      
from time import sleep, strftime, time
import matplotlib.pyplot as plt

cpu_percent = psutil.cpu_percent(interval=1) # read cpu_percent information

plt.ion()  # Turn the interactive mode on.
x = []
y = []

def write_cpu(cpu):  # write a csv file for loging data
    with open("C:\Changlei_files\work\python_codes\cpu_percent.csv", "a") as log:
        log.write("{0},{1}\n".format(strftime("%S"),str(cpu)))  #%Y-%m-%d %H:%M:%S

def graph(CPU): # def a function to plot data
    y.append(CPU)
    x.append(time())
   # plt.ion() 
    plt.clf() #clears the entire current figure with all its axes, but leaves the window opened, such that it may be reused for other plots
    plt.scatter(x,y)
    plt.plot(x,y)
    plt.xlabel("time()")
    plt.ylabel("cpu_usage/%")
    plt.draw()
   # time.sleep(0.1)
    plt.pause(0.0001)  #20181115 added, key codes 
    plt.show
count = 0
while count < 30:
    CPU = cpu_percent 
    write_cpu(CPU)
    graph(CPU)
    sleep(0.1)
    count = count + 1
    
# 20181115 note： need to learn how to transfer time scale. 

# really ?
## I delete demo1 !
