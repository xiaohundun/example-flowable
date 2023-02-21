# example-flowable
Reproduce flowable issue #3602

1. Execute ```flowable.mysql.all.create.sql``` in mysql 5.7
2. Run ```FlowableApplication.java```
3. Call ```http://127.0.0.1:8899/flowable/process-api/management/tables```

# Logs
```

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.6)

2023-02-21 09:42:07.497  INFO 10767 --- [           main] example.FlowableApplication              : Starting FlowableApplication using Java 17.0.6 on zhoujingsendeMacBook-Pro-2.local with PID 10767 (/Users/zhoujingsen/Downloads/example-flowable/target/classes started by zhoujingsen in /Users/zhoujingsen/Downloads/example-flowable)
2023-02-21 09:42:07.498  INFO 10767 --- [           main] example.FlowableApplication              : No active profile set, falling back to 1 default profile: "default"
2023-02-21 09:42:07.997  INFO 10767 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8899 (http)
2023-02-21 09:42:08.002  INFO 10767 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2023-02-21 09:42:08.002  INFO 10767 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.69]
2023-02-21 09:42:08.054  INFO 10767 --- [           main] o.a.c.c.C.[.[localhost].[/flowable]      : Initializing Spring embedded WebApplicationContext
2023-02-21 09:42:08.055  INFO 10767 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 537 ms
2023-02-21 09:42:08.233  INFO 10767 --- [           main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2023-02-21 09:42:08.281  INFO 10767 --- [           main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
2023-02-21 09:42:08.302  INFO 10767 --- [           main] o.f.s.b.app.AppEngineAutoConfiguration   : No deployment resources were found for autodeployment
2023-02-21 09:42:08.333  INFO 10767 --- [           main] o.f.s.b.ProcessEngineAutoConfiguration   : No deployment resources were found for autodeployment
2023-02-21 09:42:08.394  INFO 10767 --- [           main] o.f.s.b.c.CmmnEngineAutoConfiguration    : No deployment resources were found for autodeployment
2023-02-21 09:42:08.426  INFO 10767 --- [           main] o.f.s.b.dmn.DmnEngineAutoConfiguration   : No deployment resources were found for autodeployment
2023-02-21 09:42:08.438  INFO 10767 --- [           main] o.f.s.b.f.FormEngineAutoConfiguration    : No deployment resources were found for autodeployment
2023-02-21 09:42:08.454  INFO 10767 --- [           main] o.f.s.b.e.EventRegistryAutoConfiguration : No deployment resources were found for autodeployment
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Found 7 Engine Configurators in total:
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.engine.spring.configurator.SpringProcessEngineConfigurator (priority:50000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.eventregistry.spring.configurator.SpringEventRegistryConfigurator (priority:100000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.idm.spring.configurator.SpringIdmEngineConfigurator (priority:150000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.dmn.spring.configurator.SpringDmnEngineConfigurator (priority:200000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.form.spring.configurator.SpringFormEngineConfigurator (priority:300000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.content.spring.configurator.SpringContentEngineConfigurator (priority:400000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : class org.flowable.cmmn.spring.configurator.SpringCmmnEngineConfigurator (priority:500000)
2023-02-21 09:42:08.464  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.engine.spring.configurator.SpringProcessEngineConfigurator (priority:50000)
2023-02-21 09:42:08.488  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.eventregistry.spring.configurator.SpringEventRegistryConfigurator (priority:100000)
2023-02-21 09:42:08.490  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.idm.spring.configurator.SpringIdmEngineConfigurator (priority:150000)
2023-02-21 09:42:08.491  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.dmn.spring.configurator.SpringDmnEngineConfigurator (priority:200000)
2023-02-21 09:42:08.494  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.form.spring.configurator.SpringFormEngineConfigurator (priority:300000)
2023-02-21 09:42:08.496  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.content.spring.configurator.SpringContentEngineConfigurator (priority:400000)
2023-02-21 09:42:08.497  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing beforeInit() of class org.flowable.cmmn.spring.configurator.SpringCmmnEngineConfigurator (priority:500000)
2023-02-21 09:42:09.084  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.engine.spring.configurator.SpringProcessEngineConfigurator (priority:50000)
2023-02-21 09:42:15.363  INFO 10767 --- [           main] o.f.engine.impl.ProcessEngineImpl        : ProcessEngine default created
2023-02-21 09:42:15.410  INFO 10767 --- [           main] o.f.e.impl.cmd.ValidateV5EntitiesCmd     : Total of v5 deployments found: 0
2023-02-21 09:42:15.486  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.eventregistry.spring.configurator.SpringEventRegistryConfigurator (priority:100000)
2023-02-21 09:42:16.287  INFO 10767 --- [           main] liquibase.servicelocator                 : Cannot load service: liquibase.license.LicenseService: Provider liquibase.license.pro.DaticalTrueLicenseService could not be instantiated
2023-02-21 09:42:16.541  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully acquired change log lock
2023-02-21 09:42:16.864  INFO 10767 --- [           main] liquibase.changelog                      : Reading from act2.FLW_EV_DATABASECHANGELOG
2023-02-21 09:42:17.118  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully released change log lock
2023-02-21 09:42:17.135  INFO 10767 --- [           main] o.f.e.impl.EventRegistryEngineImpl       : EventRegistryEngine default created
2023-02-21 09:42:17.136  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.idm.spring.configurator.SpringIdmEngineConfigurator (priority:150000)
2023-02-21 09:42:17.826  INFO 10767 --- [           main] o.f.idm.engine.impl.IdmEngineImpl        : IdmEngine default created
2023-02-21 09:42:17.830  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.dmn.spring.configurator.SpringDmnEngineConfigurator (priority:200000)
2023-02-21 09:42:18.742  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully acquired change log lock
2023-02-21 09:42:18.997  INFO 10767 --- [           main] liquibase.changelog                      : Reading from act2.ACT_DMN_DATABASECHANGELOG
2023-02-21 09:42:19.226  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully released change log lock
2023-02-21 09:42:19.243  INFO 10767 --- [           main] o.f.dmn.engine.impl.DmnEngineImpl        : DmnEngine default created
2023-02-21 09:42:19.245  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.form.spring.configurator.SpringFormEngineConfigurator (priority:300000)
2023-02-21 09:42:20.169  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully acquired change log lock
2023-02-21 09:42:20.403  INFO 10767 --- [           main] liquibase.changelog                      : Reading from act2.ACT_FO_DATABASECHANGELOG
2023-02-21 09:42:20.643  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully released change log lock
2023-02-21 09:42:20.662  INFO 10767 --- [           main] o.f.form.engine.impl.FormEngineImpl      : FormEngine default created
2023-02-21 09:42:20.664  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.content.spring.configurator.SpringContentEngineConfigurator (priority:400000)
2023-02-21 09:42:20.668  INFO 10767 --- [           main] o.f.c.s.SpringContentEngineConfiguration : Content file system root : /Users/zhoujingsen/content
2023-02-21 09:42:21.563  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully acquired change log lock
2023-02-21 09:42:21.781  INFO 10767 --- [           main] liquibase.changelog                      : Reading from act2.ACT_CO_DATABASECHANGELOG
2023-02-21 09:42:22.010  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully released change log lock
2023-02-21 09:42:22.031  INFO 10767 --- [           main] o.f.c.engine.impl.ContentEngineImpl      : ContentEngine default created
2023-02-21 09:42:22.032  INFO 10767 --- [           main] o.f.a.s.SpringAppEngineConfiguration     : Executing configure() of class org.flowable.cmmn.spring.configurator.SpringCmmnEngineConfigurator (priority:500000)
2023-02-21 09:42:27.712  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully acquired change log lock
2023-02-21 09:42:27.954  INFO 10767 --- [           main] liquibase.changelog                      : Reading from act2.ACT_CMMN_DATABASECHANGELOG
2023-02-21 09:42:28.201  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully released change log lock
2023-02-21 09:42:28.222  INFO 10767 --- [           main] o.f.cmmn.engine.impl.CmmnEngineImpl      : CmmnEngine default created
2023-02-21 09:42:30.447  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully acquired change log lock
2023-02-21 09:42:30.689  INFO 10767 --- [           main] liquibase.changelog                      : Reading from act2.ACT_APP_DATABASECHANGELOG
2023-02-21 09:42:30.920  INFO 10767 --- [           main] liquibase.lockservice                    : Successfully released change log lock
2023-02-21 09:42:30.939  INFO 10767 --- [           main] o.f.app.engine.impl.AppEngineImpl        : AppEngine default created
2023-02-21 09:42:31.083  INFO 10767 --- [           main] o.f.j.s.i.a.AbstractAsyncExecutor        : Starting up the async job executor [org.flowable.spring.job.service.SpringAsyncExecutor] for engine cmmn
2023-02-21 09:42:31.116  INFO 10767 --- [       Thread-3] o.f.j.s.i.a.ResetExpiredJobsRunnable     : starting to reset expired jobs for engine cmmn
2023-02-21 09:42:31.116  INFO 10767 --- [           main] o.f.j.s.i.a.AbstractAsyncExecutor        : Starting up the async job executor [org.flowable.spring.job.service.SpringAsyncExecutor] for engine bpmn
2023-02-21 09:42:31.117  INFO 10767 --- [       Thread-2] o.f.j.s.i.a.AcquireTimerJobsRunnable     : starting to acquire async jobs due for engine cmmn
2023-02-21 09:42:31.117  INFO 10767 --- [       Thread-1] o.f.j.s.i.a.AcquireAsyncJobsDueRunnable  : starting to acquire async jobs due for engine cmmn
2023-02-21 09:42:31.198  INFO 10767 --- [       Thread-5] o.f.j.s.i.a.AcquireTimerJobsRunnable     : starting to acquire async jobs due for engine bpmn
2023-02-21 09:42:31.198  INFO 10767 --- [       Thread-4] o.f.j.s.i.a.AcquireAsyncJobsDueRunnable  : starting to acquire async jobs due for engine bpmn
2023-02-21 09:42:31.198  INFO 10767 --- [       Thread-6] o.f.j.s.i.a.ResetExpiredJobsRunnable     : starting to reset expired jobs for engine bpmn
2023-02-21 09:42:31.208  INFO 10767 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8899 (http) with context path '/flowable'
2023-02-21 09:42:31.215  INFO 10767 --- [           main] example.FlowableApplication              : Started FlowableApplication in 23.899 seconds (JVM running for 24.142)
2023-02-21 09:42:35.383  INFO 10767 --- [nio-8899-exec-1] o.a.c.c.C.[.[localhost].[/flowable]      : Initializing Spring DispatcherServlet 'Flowable BPMN Rest API'
2023-02-21 09:42:35.383  INFO 10767 --- [nio-8899-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'Flowable BPMN Rest API'
2023-02-21 09:42:35.585  INFO 10767 --- [nio-8899-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 202 ms
2023-02-21 09:42:36.559 ERROR 10767 --- [nio-8899-exec-1] o.f.c.r.e.BaseExceptionHandlerAdvice     : Unhandled exception

org.flowable.common.engine.api.FlowableException: couldn't get table counts
	at org.flowable.common.engine.impl.persistence.entity.TableDataManagerImpl.getTableCount(TableDataManagerImpl.java:59) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cmd.GetTableCountCmd.execute(GetTableCountCmd.java:36) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cmd.GetTableCountCmd.execute(GetTableCountCmd.java:24) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker$1.run(CommandInvoker.java:67) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker.executeOperation(CommandInvoker.java:140) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker.executeOperations(CommandInvoker.java:114) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker.execute(CommandInvoker.java:72) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.BpmnOverrideContextInterceptor.execute(BpmnOverrideContextInterceptor.java:26) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.interceptor.TransactionContextInterceptor.execute(TransactionContextInterceptor.java:53) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.interceptor.CommandContextInterceptor.execute(CommandContextInterceptor.java:105) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.spring.SpringTransactionInterceptor.lambda$execute$0(SpringTransactionInterceptor.java:57) ~[flowable-spring-common-6.8.0.jar:6.8.0]
	at org.springframework.transaction.support.TransactionTemplate.execute(TransactionTemplate.java:140) ~[spring-tx-5.3.24.jar:5.3.24]
	at org.flowable.common.spring.SpringTransactionInterceptor.execute(SpringTransactionInterceptor.java:57) ~[flowable-spring-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.interceptor.LogInterceptor.execute(LogInterceptor.java:30) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cfg.CommandExecutorImpl.execute(CommandExecutorImpl.java:56) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cfg.CommandExecutorImpl.execute(CommandExecutorImpl.java:51) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.ManagementServiceImpl.getTableCount(ManagementServiceImpl.java:122) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.rest.service.api.management.TableCollectionResource.getTables(TableCollectionResource.java:58) ~[flowable-rest-6.8.0.jar:6.8.0]
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[na:na]
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77) ~[na:na]
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[na:na]
	at java.base/java.lang.reflect.Method.invoke(Method.java:568) ~[na:na]
	at org.springframework.web.method.support.InvocableHandlerMethod.doInvoke(InvocableHandlerMethod.java:205) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.method.support.InvocableHandlerMethod.invokeForRequest(InvocableHandlerMethod.java:150) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:117) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:895) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:808) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1071) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:964) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:1006) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:898) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:670) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:883) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:779) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:227) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:53) ~[tomcat-embed-websocket-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:100) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.FormContentFilter.doFilterInternal(FormContentFilter.java:93) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:201) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:177) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:97) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:541) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:135) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:92) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:78) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:360) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:399) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:65) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:891) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1784) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1191) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at java.base/java.lang.Thread.run(Thread.java:833) ~[na:na]
Caused by: org.apache.ibatis.exceptions.PersistenceException: 
### Error querying database.  Cause: java.sql.SQLSyntaxErrorException: Table 'act2.act_ru_integration' doesn't exist
### The error may exist in org/flowable/common/db/mapping/entity/TableData.xml
### The error may involve org.flowable.common.engine.impl.TablePageMap.selectTableCount-Inline
### The error occurred while setting parameters
### SQL: select count(*) from ACT_RU_INTEGRATION
### Cause: java.sql.SQLSyntaxErrorException: Table 'act2.act_ru_integration' doesn't exist
	at org.apache.ibatis.exceptions.ExceptionFactory.wrapException(ExceptionFactory.java:30) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:153) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:145) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:140) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectOne(DefaultSqlSession.java:76) ~[mybatis-3.5.10.jar:3.5.10]
	at org.flowable.common.engine.impl.db.DbSqlSession.selectOne(DbSqlSession.java:286) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.persistence.entity.TableDataManagerImpl.getTableCount(TableDataManagerImpl.java:138) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.persistence.entity.TableDataManagerImpl.getTableCount(TableDataManagerImpl.java:55) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	... 67 common frames omitted
Caused by: java.sql.SQLSyntaxErrorException: Table 'act2.act_ru_integration' doesn't exist
	at com.mysql.cj.jdbc.exceptions.SQLError.createSQLException(SQLError.java:120) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.mysql.cj.jdbc.exceptions.SQLExceptionsMapping.translateException(SQLExceptionsMapping.java:122) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.mysql.cj.jdbc.ClientPreparedStatement.executeInternal(ClientPreparedStatement.java:953) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.mysql.cj.jdbc.ClientPreparedStatement.execute(ClientPreparedStatement.java:371) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.alibaba.druid.pool.DruidPooledPreparedStatement.execute(DruidPooledPreparedStatement.java:497) ~[druid-1.1.22.jar:1.1.22]
	at org.apache.ibatis.executor.statement.PreparedStatementHandler.query(PreparedStatementHandler.java:64) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.statement.RoutingStatementHandler.query(RoutingStatementHandler.java:79) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.SimpleExecutor.doQuery(SimpleExecutor.java:63) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.BaseExecutor.queryFromDatabase(BaseExecutor.java:325) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.BaseExecutor.query(BaseExecutor.java:156) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.CachingExecutor.query(CachingExecutor.java:109) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.CachingExecutor.query(CachingExecutor.java:89) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:151) ~[mybatis-3.5.10.jar:3.5.10]
	... 73 common frames omitted

2023-02-21 09:42:36.567  WARN 10767 --- [nio-8899-exec-1] .m.m.a.ExceptionHandlerExceptionResolver : Failure in @ExceptionHandler org.flowable.common.rest.exception.BaseExceptionHandlerAdvice#handleOtherException(Exception)

java.lang.NoClassDefFoundError: com/fasterxml/jackson/annotation/JsonKey
	at com.fasterxml.jackson.databind.introspect.JacksonAnnotationIntrospector.hasAsKey(JacksonAnnotationIntrospector.java:1094) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.AnnotationIntrospectorPair.hasAsKey(AnnotationIntrospectorPair.java:619) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.POJOPropertiesCollector._addFields(POJOPropertiesCollector.java:496) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.POJOPropertiesCollector.collectAll(POJOPropertiesCollector.java:421) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.POJOPropertiesCollector.getJsonValueAccessor(POJOPropertiesCollector.java:270) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.BasicBeanDescription.findJsonValueAccessor(BasicBeanDescription.java:258) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BasicSerializerFactory.findSerializerByAnnotations(BasicSerializerFactory.java:391) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BeanSerializerFactory._createSerializer2(BeanSerializerFactory.java:224) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BeanSerializerFactory.createSerializer(BeanSerializerFactory.java:173) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._createUntypedSerializer(SerializerProvider.java:1495) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._createAndCacheUntypedSerializer(SerializerProvider.java:1443) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._findExplicitUntypedSerializer(SerializerProvider.java:1412) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.DefaultSerializerProvider.hasSerializerFor(DefaultSerializerProvider.java:260) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ObjectMapper.canSerialize(ObjectMapper.java:3431) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.canWrite(AbstractJackson2HttpMessageConverter.java:275) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.http.converter.AbstractGenericHttpMessageConverter.canWrite(AbstractGenericHttpMessageConverter.java:76) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.AbstractMessageConverterMethodProcessor.getProducibleMediaTypes(AbstractMessageConverterMethodProcessor.java:380) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.AbstractMessageConverterMethodProcessor.writeWithMessageConverters(AbstractMessageConverterMethodProcessor.java:230) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestResponseBodyMethodProcessor.handleReturnValue(RequestResponseBodyMethodProcessor.java:183) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.method.support.HandlerMethodReturnValueHandlerComposite.handleReturnValue(HandlerMethodReturnValueHandlerComposite.java:78) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:135) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.ExceptionHandlerExceptionResolver.doResolveHandlerMethodException(ExceptionHandlerExceptionResolver.java:428) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.handler.AbstractHandlerMethodExceptionResolver.doResolveException(AbstractHandlerMethodExceptionResolver.java:75) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.handler.AbstractHandlerExceptionResolver.resolveException(AbstractHandlerExceptionResolver.java:142) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.handler.HandlerExceptionResolverComposite.resolveException(HandlerExceptionResolverComposite.java:80) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.processHandlerException(DispatcherServlet.java:1331) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.processDispatchResult(DispatcherServlet.java:1142) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1088) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:964) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:1006) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:898) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:670) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:883) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:779) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:227) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:53) ~[tomcat-embed-websocket-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:100) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.FormContentFilter.doFilterInternal(FormContentFilter.java:93) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:201) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:177) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:97) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:541) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:135) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:92) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:78) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:360) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:399) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:65) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:891) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1784) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1191) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at java.base/java.lang.Thread.run(Thread.java:833) ~[na:na]
Caused by: java.lang.ClassNotFoundException: com.fasterxml.jackson.annotation.JsonKey
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641) ~[na:na]
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188) ~[na:na]
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:520) ~[na:na]
	... 67 common frames omitted

2023-02-21 09:42:36.568 ERROR 10767 --- [nio-8899-exec-1] o.a.c.c.C.[.[.[.[Flowable BPMN Rest API] : Servlet.service() for servlet [Flowable BPMN Rest API] in context with path [/flowable] threw exception [Request processing failed; nested exception is org.flowable.common.engine.api.FlowableException: couldn't get table counts] with root cause

java.sql.SQLSyntaxErrorException: Table 'act2.act_ru_integration' doesn't exist
	at com.mysql.cj.jdbc.exceptions.SQLError.createSQLException(SQLError.java:120) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.mysql.cj.jdbc.exceptions.SQLExceptionsMapping.translateException(SQLExceptionsMapping.java:122) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.mysql.cj.jdbc.ClientPreparedStatement.executeInternal(ClientPreparedStatement.java:953) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.mysql.cj.jdbc.ClientPreparedStatement.execute(ClientPreparedStatement.java:371) ~[mysql-connector-java-8.0.28.jar:8.0.28]
	at com.alibaba.druid.pool.DruidPooledPreparedStatement.execute(DruidPooledPreparedStatement.java:497) ~[druid-1.1.22.jar:1.1.22]
	at org.apache.ibatis.executor.statement.PreparedStatementHandler.query(PreparedStatementHandler.java:64) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.statement.RoutingStatementHandler.query(RoutingStatementHandler.java:79) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.SimpleExecutor.doQuery(SimpleExecutor.java:63) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.BaseExecutor.queryFromDatabase(BaseExecutor.java:325) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.BaseExecutor.query(BaseExecutor.java:156) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.CachingExecutor.query(CachingExecutor.java:109) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.executor.CachingExecutor.query(CachingExecutor.java:89) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:151) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:145) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectList(DefaultSqlSession.java:140) ~[mybatis-3.5.10.jar:3.5.10]
	at org.apache.ibatis.session.defaults.DefaultSqlSession.selectOne(DefaultSqlSession.java:76) ~[mybatis-3.5.10.jar:3.5.10]
	at org.flowable.common.engine.impl.db.DbSqlSession.selectOne(DbSqlSession.java:286) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.persistence.entity.TableDataManagerImpl.getTableCount(TableDataManagerImpl.java:138) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.persistence.entity.TableDataManagerImpl.getTableCount(TableDataManagerImpl.java:55) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cmd.GetTableCountCmd.execute(GetTableCountCmd.java:36) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cmd.GetTableCountCmd.execute(GetTableCountCmd.java:24) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker$1.run(CommandInvoker.java:67) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker.executeOperation(CommandInvoker.java:140) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker.executeOperations(CommandInvoker.java:114) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.CommandInvoker.execute(CommandInvoker.java:72) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.interceptor.BpmnOverrideContextInterceptor.execute(BpmnOverrideContextInterceptor.java:26) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.interceptor.TransactionContextInterceptor.execute(TransactionContextInterceptor.java:53) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.interceptor.CommandContextInterceptor.execute(CommandContextInterceptor.java:105) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.spring.SpringTransactionInterceptor.lambda$execute$0(SpringTransactionInterceptor.java:57) ~[flowable-spring-common-6.8.0.jar:6.8.0]
	at org.springframework.transaction.support.TransactionTemplate.execute(TransactionTemplate.java:140) ~[spring-tx-5.3.24.jar:5.3.24]
	at org.flowable.common.spring.SpringTransactionInterceptor.execute(SpringTransactionInterceptor.java:57) ~[flowable-spring-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.interceptor.LogInterceptor.execute(LogInterceptor.java:30) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cfg.CommandExecutorImpl.execute(CommandExecutorImpl.java:56) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.common.engine.impl.cfg.CommandExecutorImpl.execute(CommandExecutorImpl.java:51) ~[flowable-engine-common-6.8.0.jar:6.8.0]
	at org.flowable.engine.impl.ManagementServiceImpl.getTableCount(ManagementServiceImpl.java:122) ~[flowable-engine-6.8.0.jar:6.8.0]
	at org.flowable.rest.service.api.management.TableCollectionResource.getTables(TableCollectionResource.java:58) ~[flowable-rest-6.8.0.jar:6.8.0]
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[na:na]
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77) ~[na:na]
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[na:na]
	at java.base/java.lang.reflect.Method.invoke(Method.java:568) ~[na:na]
	at org.springframework.web.method.support.InvocableHandlerMethod.doInvoke(InvocableHandlerMethod.java:205) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.method.support.InvocableHandlerMethod.invokeForRequest(InvocableHandlerMethod.java:150) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:117) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:895) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:808) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1071) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:964) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:1006) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:898) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:670) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:883) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:779) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:227) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:53) ~[tomcat-embed-websocket-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:100) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.FormContentFilter.doFilterInternal(FormContentFilter.java:93) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:201) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:177) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:97) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:541) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:135) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:92) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:78) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:360) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:399) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:65) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:891) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1784) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1191) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at java.base/java.lang.Thread.run(Thread.java:833) ~[na:na]

2023-02-21 09:42:36.570  INFO 10767 --- [nio-8899-exec-1] o.a.c.c.C.[.[localhost].[/flowable]      : Initializing Spring DispatcherServlet 'dispatcherServlet'
2023-02-21 09:42:36.570  INFO 10767 --- [nio-8899-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2023-02-21 09:42:36.571  INFO 10767 --- [nio-8899-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 1 ms
2023-02-21 09:42:36.576 ERROR 10767 --- [nio-8899-exec-1] o.a.c.c.C.[.[.[.[dispatcherServlet]      : Servlet.service() for servlet [dispatcherServlet] threw exception

java.lang.ClassNotFoundException: com.fasterxml.jackson.annotation.JsonIncludeProperties
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641) ~[na:na]
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188) ~[na:na]
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:520) ~[na:na]
	at com.fasterxml.jackson.databind.introspect.JacksonAnnotationIntrospector.findPropertyInclusionByName(JacksonAnnotationIntrospector.java:321) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.AnnotationIntrospectorPair.findPropertyInclusionByName(AnnotationIntrospectorPair.java:128) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.cfg.MapperConfigBase.getDefaultPropertyInclusions(MapperConfigBase.java:686) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BasicSerializerFactory.buildMapSerializer(BasicSerializerFactory.java:833) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BasicSerializerFactory.buildContainerSerializer(BasicSerializerFactory.java:623) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BeanSerializerFactory._createSerializer2(BeanSerializerFactory.java:204) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BeanSerializerFactory.createSerializer(BeanSerializerFactory.java:173) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._createUntypedSerializer(SerializerProvider.java:1495) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._createAndCacheUntypedSerializer(SerializerProvider.java:1443) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._findExplicitUntypedSerializer(SerializerProvider.java:1412) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.DefaultSerializerProvider.hasSerializerFor(DefaultSerializerProvider.java:260) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ObjectMapper.canSerialize(ObjectMapper.java:3431) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.canWrite(AbstractJackson2HttpMessageConverter.java:275) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.http.converter.AbstractGenericHttpMessageConverter.canWrite(AbstractGenericHttpMessageConverter.java:76) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.AbstractMessageConverterMethodProcessor.getProducibleMediaTypes(AbstractMessageConverterMethodProcessor.java:380) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.AbstractMessageConverterMethodProcessor.writeWithMessageConverters(AbstractMessageConverterMethodProcessor.java:230) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.HttpEntityMethodProcessor.handleReturnValue(HttpEntityMethodProcessor.java:219) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.method.support.HandlerMethodReturnValueHandlerComposite.handleReturnValue(HandlerMethodReturnValueHandlerComposite.java:78) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:135) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:895) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:808) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1071) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:964) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:1006) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:898) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:670) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:883) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:779) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:227) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:100) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:102) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:102) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.invoke(ApplicationDispatcher.java:711) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.processRequest(ApplicationDispatcher.java:461) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.doForward(ApplicationDispatcher.java:385) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.forward(ApplicationDispatcher.java:313) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.custom(StandardHostValve.java:403) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.status(StandardHostValve.java:249) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.throwable(StandardHostValve.java:344) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:169) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:92) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:78) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:360) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:399) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:65) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:891) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1784) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1191) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at java.base/java.lang.Thread.run(Thread.java:833) ~[na:na]

2023-02-21 09:42:36.576 ERROR 10767 --- [nio-8899-exec-1] o.a.c.c.C.[Tomcat].[localhost]           : Exception Processing ErrorPage[errorCode=0, location=/error]

org.springframework.web.util.NestedServletException: Handler dispatch failed; nested exception is java.lang.NoClassDefFoundError: com/fasterxml/jackson/annotation/JsonIncludeProperties
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1086) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:964) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:1006) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:898) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:670) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:883) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:779) ~[tomcat-embed-core-9.0.69.jar:4.0.FR]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:227) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:100) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:117) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:102) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:102) ~[spring-web-5.3.24.jar:5.3.24]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:189) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:162) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.invoke(ApplicationDispatcher.java:711) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.processRequest(ApplicationDispatcher.java:461) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.doForward(ApplicationDispatcher.java:385) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.ApplicationDispatcher.forward(ApplicationDispatcher.java:313) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.custom(StandardHostValve.java:403) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.status(StandardHostValve.java:249) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.throwable(StandardHostValve.java:344) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:169) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:92) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:78) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:360) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:399) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:65) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:891) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1784) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1191) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) ~[tomcat-embed-core-9.0.69.jar:9.0.69]
	at java.base/java.lang.Thread.run(Thread.java:833) ~[na:na]
Caused by: java.lang.NoClassDefFoundError: com/fasterxml/jackson/annotation/JsonIncludeProperties
	at com.fasterxml.jackson.databind.introspect.JacksonAnnotationIntrospector.findPropertyInclusionByName(JacksonAnnotationIntrospector.java:321) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.introspect.AnnotationIntrospectorPair.findPropertyInclusionByName(AnnotationIntrospectorPair.java:128) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.cfg.MapperConfigBase.getDefaultPropertyInclusions(MapperConfigBase.java:686) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BasicSerializerFactory.buildMapSerializer(BasicSerializerFactory.java:833) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BasicSerializerFactory.buildContainerSerializer(BasicSerializerFactory.java:623) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BeanSerializerFactory._createSerializer2(BeanSerializerFactory.java:204) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.BeanSerializerFactory.createSerializer(BeanSerializerFactory.java:173) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._createUntypedSerializer(SerializerProvider.java:1495) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._createAndCacheUntypedSerializer(SerializerProvider.java:1443) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.SerializerProvider._findExplicitUntypedSerializer(SerializerProvider.java:1412) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ser.DefaultSerializerProvider.hasSerializerFor(DefaultSerializerProvider.java:260) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at com.fasterxml.jackson.databind.ObjectMapper.canSerialize(ObjectMapper.java:3431) ~[jackson-databind-2.13.4.2.jar:2.13.4.2]
	at org.springframework.http.converter.json.AbstractJackson2HttpMessageConverter.canWrite(AbstractJackson2HttpMessageConverter.java:275) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.http.converter.AbstractGenericHttpMessageConverter.canWrite(AbstractGenericHttpMessageConverter.java:76) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.AbstractMessageConverterMethodProcessor.getProducibleMediaTypes(AbstractMessageConverterMethodProcessor.java:380) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.AbstractMessageConverterMethodProcessor.writeWithMessageConverters(AbstractMessageConverterMethodProcessor.java:230) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.HttpEntityMethodProcessor.handleReturnValue(HttpEntityMethodProcessor.java:219) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.method.support.HandlerMethodReturnValueHandlerComposite.handleReturnValue(HandlerMethodReturnValueHandlerComposite.java:78) ~[spring-web-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:135) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:895) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:808) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87) ~[spring-webmvc-5.3.24.jar:5.3.24]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1071) ~[spring-webmvc-5.3.24.jar:5.3.24]
	... 38 common frames omitted
Caused by: java.lang.ClassNotFoundException: com.fasterxml.jackson.annotation.JsonIncludeProperties
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641) ~[na:na]
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188) ~[na:na]
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:520) ~[na:na]
	... 61 common frames omitted
```