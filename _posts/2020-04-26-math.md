---
layout: single
title:  "greedyAlgorithm"
date:   2020-04-26 15:01:19 +0900
categories: homework
---

# 신박한 그리디 알고리즘

## 이집티안 분수

* 이집티안 분수는 분자가 1인 분수들을 말한다고 합니다.

예를 들어 2/3 같은경우 1/2와 1/6의 합으로 나타낼 수 있고 그 결과는 2/3=1/2+6/1로 나타낼 수 있는데

우변의 분수들을 이집티안 분수라고 말합니다.

마찬가지로 5/8은 1/2와 1/8의 합, 이집티안 분수로 나타낼 수 있다고 합니다.



* 푸는방식:

  A/B에 대한 가장 큰 단위분수는 1/(B/A+1)이 됩니다.

  예를 들어 6/14를 생각해보면 B/A=2가 되고 1/(2+1)=1/3이 됩니다.

  따라서 첫 번쨰 단위 분수는 1/3이 되며 첫번째 단위 분수를 빼고

  남은 수에서 가장 큰 단위분수를 찾아야 하는데,

  나머지는 (6/14-1/3)=4/42에 대해 위 과정을 반복하다가 분자%분모=0 이 되는 경우에

  더 이상 진행하지 않고 1/분자를 출력하고 재귀를 빠져나가면 되는데,

  이 과정에서 그리디 알고리즘을 활용한다고 합니다.

  

  

```java
package algorithm;

public class Main{
    public static void egyptian(int a,int b){
        if(a==0||b==0)
            return;
        System.out.println("a="+a+" b="+b);
    }
    if(b%a==0){
        System.out.println("1/"+b/a);
        return;
    }
    
    int danwibunsu=b/a+1;
     System.out.println("1/"+danwibunsu);
    egyptian(a*danwibunsu-b,b*danwibunsu);
}
    public static void main(String[] args){
        egyptian(2,3);
    }
}
```





