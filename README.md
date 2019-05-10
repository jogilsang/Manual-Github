# Manual-Github

### 성공적인 Git 브랜치 모델
https://nvie.com/posts/a-successful-git-branching-model/

### 정리
Git은 업데이트 이력이 남고, 동시에 여러 사람이 같은 파일을 덮어씌운다던가 하는 실수를 미연에 방지할수있는 훌륭한 통합시스템이다.  
Git에서 저장소는 repository 라고 한다. 로컬과 원격 repository로 나뉘게 되며, 로컬의 경우 컴퓨터  
원격의 경우 Git서버라고 보면되겠다. pull, push, clone 세가지 기능이 있다  
pull의 경우 최신이력이 반영된 프로젝트 내용을 받아서 업데이트 하는것, push의 경우 현재 내용을 넣는것(?)  
clone의 경우 최신이력이 반영된 프로젝트 파일 자체를 받는것이다  

폴더를 작업트리(worktree)라고 하는대, 커밋까지 세개의 절차가있다  
작업트리에서 인덱스로 등록하는 과정을 스테이징이라고하고, 그다음 인덱스에서 repository로 커밋하는것이다.  
따라서 중간에 인덱스 과정이 생략될수없으며, 원하는 파일만큼 commit 하려고할떄 파일을 골라내는것이 스테이징이다.  

브랜치는 독립적으로 어떤 작업을 진행하기 위한 개념으로, 여러작업을 동시에 진행할수있다.  
예를들면 릴리스 버전이력,기능 추가이력, 버그 수정이력 등이 있다.  
팀내에서 상의해야할부분은 어느 시점에서 브랜치들을 통합할지 여부, 브랜치 이름의 규칙, 어떤 상황에서 브랜치를 만들가이다  

브랜치는 master, hotfix, release, develop, feature 다섯가지로 나뉜다.  
master 브랜치의 경우 안정적이며, 언제든지 배포가 가능한 상태이다. 또한 version0.1 같이 배포번호가 기록된다  
develop 브랜치가 대게 통합브런치 역활을 하며, 해당 브런치를 기반으로 개발된다.  
release 브랜치의 경우 모든 기능이 동작되는지 확인하는 브런치다. 배포하게 되는경우 해당내용을 반영해서 develop 브런치에도 반영한다.  
hotfix는 긴급하게 발생한 버그를 수정하기 위한 브런치로, 대게 master 브런치에서 가져오게되며 수정사항은 develop 브런치에도 반영한다.  
feature 브런치는 토픽브런치라고도 하며, 기능추가,버그수정 등 단위작업을 수행한다. 작업이 다 완료되면 통합브런치에 합치고, 관련사항을 공유한다.  
피처브런치(토픽브런치)를 통합브런치에 합친다던가, 브런치  쓰이는 기능은 merge와 rebase 두가지가있다.  

브랜치를 전환하는 작업의 command를 checkout이라고한다.   
해당 브런치의 최상단 케이스를 Head라고 하며, 그 이전 케이스들은 ^(캐럿), ~(틸드)를 head와 같이 기술하여 표현할수있다.  
stash는 임시저장소로 커밋하지않은 상태에서 브런치를 변경하게될때, 임시로 변경사항들을 저장한다음 변경된 브런치에서 커밋할떄 사용한다.  


### 링크
- Github 사용법 및 올리는법 - 시행착오 많이겪음 및 에러 해결

https://blog.naver.com/jogilsang/221236806980

```
(remote del)
git remote -v
git remote rm origin

(readme)
 echo "# android-template-2" >> README.md

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

(특정경로,특정폴더)
copyGit -> 폴더이름
.git/info/sparse-checkout -> 옵션이름

git init copyGit
cd copyGit
git config core.sparseCheckout true
git remote add -f origin <REMOTE_URL>
echo "you want folder" >> .git/info/sparse-checkout
git pull origin master

ex : echo "MyTabLayout/etc" >> .git/info/sparse-checkout

src : https://www.lesstif.com/pages/viewpage.action?pageId=20776761

(down)
git clone [git address]
git pull [git address]
```




- Github의 Fork한 Repository 삭제

https://blog.naver.com/jogilsang/221377073174

<hr/>

### 툴바 메뉴 설정 색깔 toolbar menu setting color

세팅
```
    <style name="MainTheme.NoActionBar" parent="@style/Theme.AppCompat.DayNight.NoActionBar">
        <!-- Customize color of menu icon in toolbar. -->
        <item name="android:textColorSecondary">@color/color_main</item>

    </style>
```

설정  
```
    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.menu_main, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle item selection
        switch (item.getItemId()) {

            case R.id.action_settings:

                //startSettings();

                return true;


            case R.id.action_exit:

                actionExit();

                return true;


            default:
                return super.onOptionsItemSelected(item);
        }
    }
```

### nestedscrollview 네스티드스크롤뷰 중앙정렬 center align
```
<android.support.v4.widget.NestedScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">


    <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:card_view="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:padding="8dp"
        android:layout_gravity="center"
        android:gravity="center"
        >
```

### tablayout tab scroll 텝스크롤 탭스크롤 
```
        tabLayout.setTabGravity(TabLayout.GRAVITY_FILL);
        tabLayout.setTabMode(TabLayout.MODE_SCROLLABLE);
       
```

### 타이틀바 상태바 액션바 titlebar actionbar bar
android:theme="@android:style/Theme.NoTitleBar"  

<style name="Theme.MyDialog" parent="@style/Theme.AppCompat.Light.Dialog">
    <item name="windowActionBar">false</item>
    <item name="windowNoTitle">true</item>
</style>


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



