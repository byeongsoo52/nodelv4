# nodelv4

ERD : https://drawsql.app/teams/bs52s-team/diagrams/node-lv4

1. 좋아요 API는 어떻게 구현하였나요? 만약 1개로 구현하였다면, 분기 처리는 어떻게 처리하였나요?

Likes 모델을 사용해 postId와 userId를 조건으로 좋아요 정보를 조회한 후
좋아요 정보가 없으면 새로운 좋아요를 등록, 정보가 있으면 해당 좋아요를 삭제하는 방식입니다. 트랜잭션을 통해 이 작업이 이루어집니다.

3. 게시글 조회에서 좋아요 갯수는 어떻게 가져왔나요? 구현한 방법이 가장 효율적인 방법이었을까요?

Posts 테이블에 likes 컬럼을 추가해줬고, Likes 테이블과 Posts 모델의 관계를 include 구문을 이용해 연결된 게시글 정보를 가져오게 하였습니다. 
