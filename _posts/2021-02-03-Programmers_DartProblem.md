---
title : "[프로그래머스] [1차]다트 게임"
excerpt: "코딩테스트연습 / 2018 KAKAO BLIND RECRUITMENT"

categories:
  - Algorithm
  - Programmers
tags:
  - Algorithm
  - Programmers
---

# [1차 다트게임]

```cpp
#include <string>
#include <vector>

using namespace std;

int solution(string dartResult) {
    int answer = 0;
    int count = -1;
    vector<int> vec;
    for(int i = 0 ; i < dartResult.length() ; i++){
        
        if(dartResult[i] == 'S'){
            vec[count] = vec[count];        
        }
        else if(dartResult[i] == 'D'){
            vec[count] = vec[count] * vec[count];  
        }
        else if(dartResult[i] == 'T'){
           vec[count] = vec[count] * vec[count] * vec[count];  
        }
        
        if(dartResult[i] == '*'){
            if(count == 0){
                vec[count] = vec[count] *2;
            }
            else{
                vec[count-1] *= 2;
                vec[count] *= 2;
            }
        }
        else if(dartResult[i] == '#'){
            vec[count] *= -1;
        }
        
        if(dartResult[i] == '1'){
            if(dartResult[i+1] == '0'){
                vec.push_back(10);
                i += 1;
            }
            else{
                vec.push_back(1);
            }
            count++;
        }
        else if(dartResult[i] > 46 && dartResult[i] < 58){
            vec.push_back(dartResult[i] - 48);
            count++;
        }
        
    }

    for(int i = 0 ; i < vec.size(); i++){
        answer += vec[i];
    }
    return answer;
}
```
* * *
### 해설

점수계산을 하나의 백터(vec)에 담아서 계산을 하였다.

String 형에서 10을 판별할때는 맨처음이 숫자 1이면 그 다음 값이 0인지 다른것지 확인하고 if-else 문을 돌려서 확인했다.  

또한 String 값에서 0을 int형으로 변환시키면 48 이었기 때문에 나머지 값들은 모두 String 값에서 48을 뺴주었다.  

마지막으로 *인 아차상의 경우 count라는 변수를 활용하여 지금까지 숫자가 몇번 나온지를 확인하여 한번 나왔을 경우에는 그 점수에만 2배를 시키도록 예외처리를 하였다.
    


