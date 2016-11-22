springmvc_spring_mybatis_maven
==============================
## 在 mybatis_ssm基础上的进步

## 整合xml
# spring-mybatis.xml 
      <!-- myBatis文件 -->
      <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
          <property name="dataSource" ref="dataSource" />
          <!-- 自动扫描entity目录, 省掉Configuration.xml里的手工配置 -->
          <property name="mapperLocations" value="classpath:com/ssmm/mapping/*.xml" />
        </bean>
      <!-- 配置数据源 -->

      这个变化不大
# springmvc.xml
        有
        <!-- 自动扫描controller包下的所有类，使其认为spring mvc的控制器 -->
        <!-- 对模型视图名称的解析，即在模型视图名称添加前后缀 -->
        无
        <!-- 避免IE执行AJAX时,返回JSON出现下载文件 -->
        <!-- 启动Spring MVC的注解功能，完成请求和注解POJO的映射 --
        文件的配置
        <bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
            <property name="defaultEncoding">
              <value>UTF-8</value>
            </property>
            <property name="maxUploadSize">
              <value>32505856</value><!-- 上传文件大小限制为31M，31*1024*1024 -->
            </property>
            <property name="maxInMemorySize">
              <value>4096</value>
            </property>
          </bean>
          
# spring
    无
    <!-- 引入属性文件 -->
      <context:property-placeholder location="classpath:config.properties" />
    无
      <!-- 自动扫描(自动注入) -->
      <context:component-scan base-package="com.ssmm.service" />
