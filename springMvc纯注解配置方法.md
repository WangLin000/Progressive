# maven-war 插件打包配置
```html
<plugin>
    <artifactId>maven-war-plugin</artifactId>
    <version></version>
    <configuration>
        <failOnMissingWebXml>false</failOnMissingWebXml>
    </configuration>
</plugin>
```
# 替代 webxml
```java
public class WebConfig extends AbstractAnnotationConfigDispatcherServletInitializer {
    // Spring 配置类
    @Override
    protected Class<?>[] getRootConfigClasses() {
        return new Class[] {};
    }
    // SpringMvc配置类
    @Override
    protected Class<?>[] getServletConfigClasses() {
        return new Class[] { SpringMvcConfig.class };
    }
    // SpringMvc映射范围
    @Override
    protected String[] getServletMappings() {
        return new String[] { "/" };
    }

}
```
# 配置 SpringMvc
```java
@EnableWebMvc
@ComponentScan("") // 配置映射路径
public class SpringMvcConfig implements WebMvcConfigurer{
    // 可以添加其他配置
}
```