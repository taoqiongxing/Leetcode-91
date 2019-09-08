# Leetcode-91
解码方法——超简单解法

题目链接：https://leetcode-cn.com/problems/decode-ways/

    d=ord('A')-ord('1')
    ins=input()[1:-1]
    res=0
    def func(i_s,o_s):
        if len (i_s)==0:
            res+=1 #计算解码个数
        elif len (i_s)==1:
            if i_s[0]!='0':
            func(i_s[1:],o_s+chr(ord(i_s[0])+d))
        else:
            if i_s[0]!='0':
                func(i_s[1:],o_s+chr(ord(i_s[0])+d))
                if i_s[0]=='1' or (i_s[0]=='2' and i_s[1]<='6'):
                    func(i_s[2:],o_s+chr((ord(i_s[0])-ord('0'))*10+ord(i_s[1])+d))
    func(ins,'')
    print(res)
  
# 字节跳动第三批算法岗笔试-第四题(2019.09.08)

### 唯一的不同就是它是是按字典序输出，原题是计算个数

#笔试的时候可能感冒发烧状态不好，理不清思路，凉凉！线下不到不用30分钟就ac了
  
    d=ord('A')-ord('1')
    ins=input()[1:-1]
    def func(i_s,o_s):
        if len (i_s)==0:
            print(o_s) #字典序输出
        elif len (i_s)==1:
            if i_s[0]!='0':
                func(i_s[1:],o_s+chr(ord(i_s[0])+d))
        else:
            if i_s[0]!='0':
                func(i_s[1:],o_s+chr(ord(i_s[0])+d))
                if i_s[0]=='1' or (i_s[0]=='2' and i_s[1]<='6'):
                    func(i_s[2:],o_s+chr((ord(i_s[0])-ord('0'))*10+ord(i_s[1])+d))
    func(ins,'')
