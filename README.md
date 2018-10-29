# Manual-Github

### 링크
- Github 사용법 및 올리는법 - 시행착오 많이겪음 및 에러 해결

https://blog.naver.com/jogilsang/221236806980

```
(new)
git config --global user.name "jogilsang"
git config --global user.email jogilsang@gmail.com
git init
git status
git add -A
git commit -m "update"
git remote add origin [git address]
git push -f origin master

(modifyed)
git add -A
git commit -m "update"
git push -f origin master
```

- Github의 Fork한 Repository 삭제

https://blog.naver.com/jogilsang/221377073174

<hr/>

### 작성법
1. 라인피드(Linefeed)
- 줄에다가 스페이스+스페이스 를 넣는다
```
사람을 존경하라,  
그러면 그는 더 많은 일을 해 낼 것이다.
```
- 아무생각없이 엔터를 친다면, 
```
사람을 존경하라,

그러면 그는 더 많은 일을 해 낼 것이다.
```

2. 이미지 리사이즈(Image Resize)

- git 파일내부 
```
"![](/11.png)"

android : 375 x 667
```
![](/11.png)

- git 파일 리사이즈 1
```
<center><img src="/11.png" width="375" height="667"></center>
```
<center><img src="/11.png" width="375" height="667"></center>

- 웹 페이지 가져오기
```
![](https://blogpfthumb-phinf.pstatic.net/MjAxNzEyMDhfMTMy/MDAxNTEyNzA3MTc0ODA3.rbnlwP_k8OCxoan813kT-Q0DVAxw8Vgb0co6Ivpcg1Yg.QdHiNjmkf1OVkzCy8ZIyyy1cjDe2947sLVuj9vynVpQg.PNG.jogilsang/JS.png?type=w161)
```
![](https://blogpfthumb-phinf.pstatic.net/MjAxNzEyMDhfMTMy/MDAxNTEyNzA3MTc0ODA3.rbnlwP_k8OCxoan813kT-Q0DVAxw8Vgb0co6Ivpcg1Yg.QdHiNjmkf1OVkzCy8ZIyyy1cjDe2947sLVuj9vynVpQg.PNG.jogilsang/JS.png?type=w161)



