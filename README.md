# python
python 处理csv
# coding: utf-8

import csv


def liebiao(string1):
    x = ('、' in string1)
    y = ('-' in string1)

    if x&(not y):   #只包含 ，不包含 -
        print 'x=%s'%x
        print 'y=%s'%y
        first = string1.split('、')
        print string1
        return string1

    elif (not x)&y: #只包含 - 不包含 ,
        print 'x=%s'%x
        print 'y=%s'%y
        temp = i.split('-')
        print temp
        for j in range(int(temp[0]),int(temp[1])+1):
                    string1.append(j)
        print string1
        return string1

    elif x&y:   #都包含
        print 'x=%s'%x
        print 'y=%s'%y
        first = string1.split(',')
        print first
        for i in first:
            temp = i.split('-')
            for j in range(int(temp[0]),int(temp[1])+1):
                string1.append(j)
        print string1
        return string1
    else:#都不包含
        print 'x=%s'%x
        print 'y=%s'%y
        print string1
        return string1


split_liebiao=[]

string1=[]
print string1


csvfile = file('test.csv', 'rb')
reader = csv.reader(csvfile)

a_list=[]
for line in reader:
    print line[0],line[1],line[2]
    a_list.append(line)

print '\n\n'

for i in a_list:
    print i[0],i[1],i[2]
    n=liebiao(i)
    print n



csvfile.close()



