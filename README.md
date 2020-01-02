# python
파이썬 분석에서 배운 내용을 토대로 만든 코드들 
import csv
import matplotlib.pyplot as plt

f = open('201912age.csv')
data = csv.reader(f)
result1 = []
result2 = []
name1 = input('인구 구조가 알고 싶은 지역의 이름을 입력해주세요:')
name2 = input('인구 구조가 알고 싶은 지역의 이름을 입력해주세요:')
for row in data:
    if name1 in row[0] : 
        for i in row[3:]:
            result1.append(int(i.replace(',','')))
    if name2 in row[0] : 
        for i in row[3:]:
            result2.append(int(i.replace(',','')))        

plt.style.use('ggplot')
plt.rc('font',family='Malgun Gothic')
plt.title(' 지역의 인구 구조')

plt.plot(result1,'hotpink',label=name1)
plt.plot(result2,'blue',label=name2)
plt.legend()

plt.show()


//데이터 분석 책을 토대로 변형하여 2가지의 위치에 대해 서로 비교 할 수 있게 만드는 코드
