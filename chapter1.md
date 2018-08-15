## 本地单元测试

适用于没有依赖关系或只有简单的Android依赖关系，常使用mockito框架实现依赖关系

#### 配置环境

在Android studio中，单元测试文件需放在src/test/java路径下。还需添加以下依赖项

```
dependencies {

   ...
   
   // JUnit4框架，必须
    testImplementation 'junit:junit:4.12'
   // Mockito框架，可选
    testImplementation 'org.mockito:mockito-core:2.2.15'

  ...
  
}
```

> 若需与Android依赖项交互，则需要mockito，以简化测试

#### 创建本地单元测试

本地单元测试类应编写为JUnit4测试类，需要在测试方法前添加**@Test**注解，在方法中实现测试功能的逻辑代码

        @Test
        fun addition_isCorrect() {

            assertEquals(1 + 2, sum(1, 
        //等价于  assertThat(1 + 2, `is`(sum(1, 2)))2))
        //is为 Hamcrest匹配器

        }

        // 求和
        fun sum(a: Int, b: Int): Int {
            return a + b
        }

        // 测试结果
        通过


> 为了增加测试可读性，使用[Hamcrest匹配器](https://github.com/hamcrest)



