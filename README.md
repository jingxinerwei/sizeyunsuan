# sizeyunsuan
import random
 
#四则运算
 
def szys():
 
    sym = ['＋', '－', '×', '÷']
 
    f= random.randint(0, 3)
 
    n1 = random.randint(1, 10)
 
    n2 = random.randint(1, 10)
 
    result = 0
 
    if f== 0:#加法
 
       result  = n1 + n2
 
    elif f == 1:#减法，要先比较大小，防止输出负数
 
        n1, n2 = max(n1, n2), min(n1, n2)
 
        result  = n1 - n2
 
    elif f== 2:#乘法
 
        result  = n1 * n2
 
    elif f == 3:#除法，要比较大小，并循环取整除
 
        n1, n2 = max(n1, n2), min(n1, n2)
 
        while n1 % n2 != 0:
 
            n1 = random.randint(1, 10)
 
            n2 = random.randint(1, 10)
 
            n1, n2 = max(n1, n2), min(n1, n2)
 
        result  = int(n1 / n2)
 
    print(n1, sym[f], n2, '= ', end='')
 
    return result
 
  
 
#输入题目数量并开始生成对应数量的题目
 
def test():
 
    sym = ['＋', '－', '×', '÷']
 
    print('输入所需要的题目数量：')
 
    n=int(input())
 
    result =[]
 
    m=0
    i=1
    j=0
    
 
    while m<=(n-1):
        
        print(m+1,end='、')
 
        result .append(szys())
    
        s=int(input())
    
        if s == result[m] :
 
            print('正确，得10分')
            j=j+10*i
 
        else:
 
            print('错误，不得分，正确答案是', result[m] )
    
        m=m+1
       
    print('答对题数为：' , int(j/10))
    print('总计得分为：' , j )
    
        
   
    
    
test(）

