# mybatis-generator
mybatis-generator/  auto create mapper.xml,mapper.java,model.java




참고 : https://mybatis.org/generator/quickstart.html
* -> 필수 항목
<generatorConfguration>
	<context
		id : 아무거나
		targetRuntime : MyBatis3   ( MyBatis3DynamicSql / MyBatis3Kotlin / MyBatis3 / MyBatis3Simple)
	<jdbcConnection
		driverClass : db driver
		connectUrl : 
		userId :
		password : 
	/>
	
	<javaModelGenerator
	*	targetProject : vo.java 파일을 저장할 프로젝트
	*	targetPacakage : vo.java 파일 저장될 폴더위치
	/>
	<sqlMapGenerator 
	*	targetProject : mapper.xml 파일을 저장할 프로젝트
	*	targetPacakage : mapper.xml 파일 저장될 폴더위치
	/>
	<javaClientGenerator
	*	targetProject : mapper.java 파일을 저장할 프로젝트
	*	targetPacakage : mapper.java 파일 저장될 폴더위치
	/>
	
	
	<table
	*	tableName : DB 상의 테이블명
		alias : mapper.xml 상의 테이블 별칭
		mapperName : mapper.java , mapper.xml 파일명  
			모델(VO) 이름은 테이블명 그대로 사용된다.
			ex) visit -> visit.java, visit,xml
		domainObjectName : mapper.java, mapper.xml, [modelVO].java 파일명
			모델(VO) 이름도 domainName에 따라 변경된다.
			ex ) visit -> visitMapper.java, visitMapper.xml , visit.java
	>
		<generatedKey
		*	column :
		*	sqlStatement : DB 종류  (Cloudscape / DB2 / DB2_MF / Derby / HSQLDB / Informix / MySql / SqlServer / SYBASE / JDBC)
			
			1) identity : true, type : post 
			2) identity : true
			3) type : pre
			4) 생략
		/>
		
		<ignoreColumnsByRegex : 무시 컬럼 정규식 표현 
			pattern="(?i)col.*">
	        <except column="col01"/> : col01 컬럼 제외한 col.* 무시
      	</ignoreColumnsByRegex>	
	</table>
</generatorConfguration>
