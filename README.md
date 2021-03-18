# python_MySQL

### 1.파이썬 MySQL 라이브러리 (설치방법,임포트 방법 등)
 - 파이썬에서 MySQL과 연동하려면 라이브러리가 필요하다. 아래와 같이 순서대로 실행하면 된다
 -  pip install mysql-connector-python
 -  위에 코드는 파이썬에 MySQL라이브러리를 설치시키는 코드이다.
 -  import mysql-connector
 
 ### 2.python에서 Mysql 커넥션 하는법 (전용 DB유저 생성 포함)
 
 - 1. 커넥터로부터 커넥션을 받는다.
 
 -        try :
 -            connection = mysql.connector.connect(
 -               host = MySQL서버 코드,
 -               database = 데이터 베이스 입력,
 -               user =사용자 이름,
 -               password = 암호
 -           ) 
 -            if connection.is_connected() :
 -               print('연결됬을때')
 -               be_info = connection.get_server_info()
 -               print("MySQL servar version : ",be_info)

 - 2.커서를 가져온다. 
 - cursor = connection.cursor()
 
 - print('커서 가져온것 후')
 - 3. 원하는거 실행 가능.
 
 -              record = cursor.fetchone()
 -              print('Connected to be : ', record)
                
 -              cursor.executemany(query,record)
 -              connection.commit()
 
 - 4.실행 후 커서에서 결과를 빼낸다.
 -      except Error as e :
 -          print('디비 관련 에러 발생',e)
 -      finally :
 
 - 5. 모든 데이터 베이스 실행 명령을 전부 끝냈으며,커서와 커넥션을 모두 닫아준다.
 
 -         cursor.close()
 -         connection.close()
 -         print("MySQL 커넥션 종료")
 
 - 이런식으로 하면 python에서 Mysql 쓸 수 있다.
 
 
