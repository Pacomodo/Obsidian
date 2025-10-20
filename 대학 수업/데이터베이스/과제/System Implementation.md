## 테이블 : users
#### 테이블 스키마
![[Pasted image 20240625223955.png]]
#### 테이블 데이터
![[Pasted image 20240625224057.png]]
___
## 테이블 : recipe
#### 테이블 스키마
![[Pasted image 20240625224246.png]]
#### 테이블 데이터
![[Pasted image 20240625224611.png]]
너무 길어서 중략했습니다.
___
## 테이블 : review
#### 테이블 스키마
![[Pasted image 20240625224723.png]]
#### 테이블 데이터
![[Pasted image 20240625224749.png]]
___
## 테이블 : favorite
#### 테이블 스키마
![[Pasted image 20240625224854.png]]
#### 테이블 데이터
![[Pasted image 20240625224915.png]]
___
## 테이블 : subscribe
#### 테이블 스키마
![[Pasted image 20240625224944.png]]
#### 테이블 데이터
![[Pasted image 20240625225003.png]]
___
## 테이블 : ingredients
#### 테이블 스키마
![[Pasted image 20240625225251.png]]
#### 테이블 데이터
![[Pasted image 20240625225357.png]]
___
## 테이블 : cook_times
#### 테이블 스키마
![[Pasted image 20240625225449.png]]
#### 테이블 데이터
![[Pasted image 20240625225515.png]]
___
## 테이블 : category
#### 테이블 스키마
![[Pasted image 20240625225550.png]]
#### 테이블 데이터
![[Pasted image 20240625225611.png]]
___
## 테이블 : recipe_category
#### 테이블 스키마
![[Pasted image 20240625225659.png]]
#### 테이블 데이터
![[Pasted image 20240625225726.png]]
___
## 테이블 : recipe_cook_time
#### 테이블 스키마
![[Pasted image 20240625225822.png]]
#### 테이블 데이터
![[Pasted image 20240625225849.png]]
___
## 테이블 : recipe_ingredient
#### 테이블 스키마
![[Pasted image 20240625225927.png]]
#### 테이블 데이터
![[Pasted image 20240625225957.png]]
___
## 소스코드 요약 설명서

|          Code          |     Module     |                                                                               Description                                                                                |
| :--------------------: | :------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|       styles.css       |      N/A       |                                                                                                                                                                          |
|       config.php       |      N/A       |                                                                             데이터베이스 연결 설정 파일                                                                              |
|       index.php        |      N/A       | 메인 화면. favorite테이블과 recipe테이블을 join한 테이블을 select하여 즐겨찾기한 레시피를 보여주고, subscribe테이블과 recipe테이블, users테이블을 join한 테이블을 select하여 구독한 사람의 레시피를 보여준다. 그 외에도 메인메뉴들을 상단에 띄우는 코드이다. |
|       login.php        |      로그인       |                                                              입력된 정보를 users테이블에서 조회(select)하여 로그인을 하는 코드이다.                                                               |
|      register.php      |     회원 등록      |                                                                 입력된 정보를 바탕으로 users테이블에 insert를 하는 코드이다.                                                                  |
|      profile.php       |    회원 정보 수정    |                                                                 입력된 정보를 바탕으로 users테이블에 update를 하는 코드이다.                                                                  |
|       logout.php       |      로그아웃      |                                                                              로그아웃을 하는 코드이다.                                                                              |
|       recipe.php       |   특정 레시피 조회    |    입력된 정보를 바탕으로 recipe테이블을 조회(select)하여 특정 레시피를 보여주는 코드이다. 더불어 특정 레시피에 달린 리뷰 및 평점, 즐겨찾기 여부, 리뷰를 할수있는 칸과 리뷰 삭제 칸 및 수정 칸도 같이 보여준다. 이때는 review테이블과 favorite테이블을 같이 조회한다.    |
|     add_recipe.php     |     레시피 추가     |                                                                 입력된 정보를 바탕으로 recipe테이블에 insert를 하는 코드이다.                                                                 |
|    edit_recipe.php     |     레시피 수정     |                                                               입력된 정보를 바탕으로 recipe테이블의 레시피를 update하는 코드이다.                                                                |
|   delete_recipe.php    |     레시피 삭제     |                                                                입력된 정보를 바탕으로 recipe테이블의 특정 레시피를 삭제하는 코드이다.                                                                |
|     add_review.php     |     리뷰 추가      |                                                         recipe.php를 통해 입력된 정보를 바탕으로 review테이블에 insert를 하는 코드이다.                                                          |
|    edit_review.php     |     리뷰 수정      |                                                         recipe.php를 통해 입력된 정보를 바탕으로 review테이블에 update를 하는 코드이다.                                                          |
|   delete_review.php    |     리뷰 삭제      |                                                        recipe.php를 통해 입력된 정보를 바탕으로 review테이블의 리뷰를 delete하는 코드이다.                                                         |
|   subscriptions.php    |     구독 관리      |                                                                subscribe테이블을 조회(select)함으로써 구독한 사용자를 찾는다.                                                                |
|     subscribe.php      |     구독 추가      |                                                               입력된 정보를 바탕으로 subscribe테이블에 insert를 하는 코드이다.                                                                |
|    unsubscribe.php     |     구독 삭제      |                                                               입력된 정보를 바탕으로 subscribe테이블에 delete를 하는 코드이다.                                                                |
|   search_results.php   |     레시피 조회     |                                                         입력된 정보를 바탕으로 레시피를 조회할 수 있는 코드이다.(recipe테이블의 select문 사용)                                                          |
|    search_user.php     |     사용자 조회     |                                                          입력된 정보를 바탕으로 사용자를 조회할 수 있는 코드이다.(users테이블의 select문 사용)                                                          |
|    add_favorite.php    |    즐겨찾기 추가     |                                                              특정 레시피를 즐겨찾기에 추가하는 코드이다.(favorite테이블에 insert)                                                               |
|  remove_favorite.php   |    즐겨찾기 제거     |                                                              특정 레시피를 즐겨찾기에서 제거하는 코드이다.(favorite테이블에 delete)                                                              |
|   manage_recipes.php   |     레시피 관리     |                                                          recipe테이블을 select문으로 사용자가 작성했던 레시피를 불러와 관리할 수 있는 코드이다.                                                          |
| subscribed_recipes.php | 구독한 사람의 레시피 보기 |                                             recipe테이블과 subscribe테이블, user테이블을 join하여 구독한 사용자의 레시피 목록을 가져와 조회할 수 있도록 하는 코드이다.                                             |


