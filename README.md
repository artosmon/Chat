package ru.sberbank.uvz3.clientexternallink.adapter.conroller;

import org.junit.jupiter.api.Test;
import org.springframework.http.MediaType;
import org.springframework.test.web.servlet.request.MockMvcRequestBuilders;
import org.springframework.test.web.servlet.result.MockMvcResultMatchers;
import ru.sberbank.uvz3.clientexternallink.CommonTest;

class AskLinkControllerTest extends CommonTest {

    @Test
    void success_response() throws Exception {
        mockMvc.perform(MockMvcRequestBuilders
                        .get("/getAskLinks/{clientId}", "fokClient")
                        .header("iv-user", "CurrentUser")
                        .contentType(MediaType.APPLICATION_JSON))
                .andExpect(MockMvcResultMatchers.status().isOk());
    }
}


Failed to load ApplicationContext for [WebMergedContextConfiguration@5f214f84 testClass = ru.sberbank.uvz3.clientexternallink.adapter.conroller.AskLinkControllerTest, locations = [], classes = [ru.sberbank.uvz3.clientexternallink.ClientExternalLinkApplication], contextInitializerClasses = [], activeProfiles = ["${spring.test.profile:test-h2}"], propertySourceDescriptors = [], propertySourceProperties = ["org.springframework.boot.test.context.SpringBootTestContextBootstrapper=true"], contextCustomizers = [org.springframework.boot.webmvc.test.autoconfigure.WebDriverContextCustomizer@4c07d1fc, org.springframework.boot.web.server.context.SpringBootTestRandomPortContextCustomizer@2506e949, org.springframework.boot.test.autoconfigure.OnFailureConditionReportContextCustomizerFactory$OnFailureConditionReportContextCustomizer@db99785, [ImportsContextCustomizer@590b1f1e key = [org.springframework.boot.webmvc.test.autoconfigure.MockMvcWebDriverAutoConfiguration, org.springframework.boot.webmvc.test.autoconfigure.MockMvcWebClientAutoConfiguration, org.springframework.boot.webmvc.test.autoconfigure.MockMvcAutoConfiguration]], org.springframework.boot.test.context.PropertyMappingContextCustomizer@2d298995, org.springframework.boot.test.context.filter.ExcludeFilterContextCustomizer@5c18d6d4, org.springframework.boot.test.json.DuplicateJsonObjectContextCustomizerFactory$DuplicateJsonObjectContextCustomizer@3daf03d8, org.springframework.test.context.support.DynamicPropertiesContextCustomizer@0, org.springframework.boot.test.context.SpringBootTestAnnotation@4928bd7a], resourceBasePath = "src/main/webapp", contextLoader = org.springframework.boot.test.context.SpringBootContextLoader, parent = null]
java.lang.IllegalStateException: Failed to load ApplicationContext for [WebMergedContextConfiguration@5f214f84 testClass = ru.sberbank.uvz3.clientexternallink.adapter.conroller.AskLinkControllerTest, locations = [], classes = [ru.sberbank.uvz3.clientexternallink.ClientExternalLinkApplication], contextInitializerClasses = [], activeProfiles = ["${spring.test.profile:test-h2}"], propertySourceDescriptors = [], propertySourceProperties = ["org.springframework.boot.test.context.SpringBootTestContextBootstrapper=true"], contextCustomizers = [org.springframework.boot.webmvc.test.autoconfigure.WebDriverContextCustomizer@4c07d1fc, org.springframework.boot.web.server.context.SpringBootTestRandomPortContextCustomizer@2506e949, org.springframework.boot.test.autoconfigure.OnFailureConditionReportContextCustomizerFactory$OnFailureConditionReportContextCustomizer@db99785, [ImportsContextCustomizer@590b1f1e key = [org.springframework.boot.webmvc.test.autoconfigure.MockMvcWebDriverAutoConfiguration, org.springframework.boot.webmvc.test.autoconfigure.MockMvcWebClientAutoConfiguration, org.springframework.boot.webmvc.test.autoconfigure.MockMvcAutoConfiguration]], org.springframework.boot.test.context.PropertyMappingContextCustomizer@2d298995, org.springframework.boot.test.context.filter.ExcludeFilterContextCustomizer@5c18d6d4, org.springframework.boot.test.json.DuplicateJsonObjectContextCustomizerFactory$DuplicateJsonObjectContextCustomizer@3daf03d8, org.springframework.test.context.support.DynamicPropertiesContextCustomizer@0, org.springframework.boot.test.context.SpringBootTestAnnotation@4928bd7a], resourceBasePath = "src/main/webapp", contextLoader = org.springframework.boot.test.context.SpringBootContextLoader, parent = null]
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.lambda$loadContext$0(DefaultCacheAwareContextLoaderDelegate.java:195)
	at org.springframework.test.context.cache.DefaultContextCache.put(DefaultContextCache.java:214)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:160)
	at org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:128)
	at org.springframework.test.context.web.ServletTestExecutionListener.setUpRequestContextIfNecessary(ServletTestExecutionListener.java:200)
	at org.springframework.test.context.web.ServletTestExecutionListener.prepareTestInstance(ServletTestExecutionListener.java:139)
	at org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:260)
	at org.springframework.test.context.junit.jupiter.SpringExtension.postProcessTestInstance(SpringExtension.java:205)
	at java.base/java.util.stream.ForEachOps$ForEachOp$OfRef.accept(ForEachOps.java:184)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1708)
	at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509)
	at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499)
	at java.base/java.util.stream.ForEachOps$ForEachOp.evaluateSequential(ForEachOps.java:151)
	at java.base/java.util.stream.ForEachOps$ForEachOp$OfRef.evaluateSequential(ForEachOps.java:174)
	at java.base/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:234)
	at java.base/java.util.stream.ReferencePipeline.forEach(ReferencePipeline.java:596)
	at java.base/java.util.Optional.orElseGet(Optional.java:364)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1596)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1596)
Caused by: java.lang.IllegalStateException: Failed to generate bean name for imported class 'ru.sberbank.uvz3.httpclient.ssl.core.RestTemplateBuilderSslConfig'
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.registerBeanDefinitionForImportedConfigurationClass(ConfigurationClassBeanDefinitionReader.java:172)
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitionsForConfigurationClass(ConfigurationClassBeanDefinitionReader.java:145)
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitions(ConfigurationClassBeanDefinitionReader.java:124)
	at org.springframework.context.annotation.ConfigurationClassPostProcessor.processConfigBeanDefinitions(ConfigurationClassPostProcessor.java:458)
	at org.springframework.context.annotation.ConfigurationClassPostProcessor.postProcessBeanDefinitionRegistry(ConfigurationClassPostProcessor.java:310)
	at org.springframework.context.support.PostProcessorRegistrationDelegate.invokeBeanDefinitionRegistryPostProcessors(PostProcessorRegistrationDelegate.java:349)
	at org.springframework.context.support.PostProcessorRegistrationDelegate.invokeBeanFactoryPostProcessors(PostProcessorRegistrationDelegate.java:118)
	at org.springframework.context.support.AbstractApplicationContext.invokeBeanFactoryPostProcessors(AbstractApplicationContext.java:794)
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:602)
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:756)
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:445)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:321)
	at org.springframework.boot.test.context.SpringBootContextLoader.lambda$loadContext$2(SpringBootContextLoader.java:156)
	at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:58)
	at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:46)
	at org.springframework.boot.SpringApplication.withHook(SpringApplication.java:1465)
	at org.springframework.boot.test.context.SpringBootContextLoader$ContextLoaderHook.run(SpringBootContextLoader.java:605)
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:156)
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:115)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContextInternal(DefaultCacheAwareContextLoaderDelegate.java:247)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.lambda$loadContext$0(DefaultCacheAwareContextLoaderDelegate.java:167)
	... 21 more
Caused by: java.lang.IllegalArgumentException: Could not find class [org.springframework.boot.web.client.RestTemplateBuilder]
	at org.springframework.util.ClassUtils.resolveClassName(ClassUtils.java:353)
	at org.springframework.core.annotation.TypeMappedAnnotation.adapt(TypeMappedAnnotation.java:451)
	at org.springframework.core.annotation.TypeMappedAnnotation.getValue(TypeMappedAnnotation.java:384)
	at org.springframework.core.annotation.TypeMappedAnnotation.asMap(TypeMappedAnnotation.java:273)
	at org.springframework.core.annotation.AbstractMergedAnnotation.asAnnotationAttributes(AbstractMergedAnnotation.java:191)
	at org.springframework.context.annotation.AnnotationBeanNameGenerator.determineBeanNameFromAnnotation(AnnotationBeanNameGenerator.java:143)
	at org.springframework.context.annotation.AnnotationBeanNameGenerator.generateBeanName(AnnotationBeanNameGenerator.java:110)
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.registerBeanDefinitionForImportedConfigurationClass(ConfigurationClassBeanDefinitionReader.java:168)
	... 41 more
Caused by: java.lang.ClassNotFoundException: org.springframework.boot.web.client.RestTemplateBuilder
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:526)
	at java.base/java.lang.Class.forName0(Native Method)
	at java.base/java.lang.Class.forName(Class.java:536)
	at java.base/java.lang.Class.forName(Class.java:515)
	at org.springframework.util.ClassUtils.forName(ClassUtils.java:302)
	at org.springframework.util.ClassUtils.resolveClassName(ClassUtils.java:343)
	... 48 more


Failed to generate bean name for imported class 'ru.sberbank.uvz3.httpclient.ssl.core.RestTemplateBuilderSslConfig'
java.lang.IllegalStateException: Failed to generate bean name for imported class 'ru.sberbank.uvz3.httpclient.ssl.core.RestTemplateBuilderSslConfig'
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.registerBeanDefinitionForImportedConfigurationClass(ConfigurationClassBeanDefinitionReader.java:172)
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitionsForConfigurationClass(ConfigurationClassBeanDefinitionReader.java:145)
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.loadBeanDefinitions(ConfigurationClassBeanDefinitionReader.java:124)
	at org.springframework.context.annotation.ConfigurationClassPostProcessor.processConfigBeanDefinitions(ConfigurationClassPostProcessor.java:458)
	at org.springframework.context.annotation.ConfigurationClassPostProcessor.postProcessBeanDefinitionRegistry(ConfigurationClassPostProcessor.java:310)
	at org.springframework.context.support.PostProcessorRegistrationDelegate.invokeBeanDefinitionRegistryPostProcessors(PostProcessorRegistrationDelegate.java:349)
	at org.springframework.context.support.PostProcessorRegistrationDelegate.invokeBeanFactoryPostProcessors(PostProcessorRegistrationDelegate.java:118)
	at org.springframework.context.support.AbstractApplicationContext.invokeBeanFactoryPostProcessors(AbstractApplicationContext.java:794)
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:602)
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:756)
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:445)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:321)
	at org.springframework.boot.test.context.SpringBootContextLoader.lambda$loadContext$2(SpringBootContextLoader.java:156)
	at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:58)
	at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:46)
	at org.springframework.boot.SpringApplication.withHook(SpringApplication.java:1465)
	at org.springframework.boot.test.context.SpringBootContextLoader$ContextLoaderHook.run(SpringBootContextLoader.java:605)
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:156)
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:115)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContextInternal(DefaultCacheAwareContextLoaderDelegate.java:247)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.lambda$loadContext$0(DefaultCacheAwareContextLoaderDelegate.java:167)
	at org.springframework.test.context.cache.DefaultContextCache.put(DefaultContextCache.java:214)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:160)
	at org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:128)
	at org.springframework.test.context.web.ServletTestExecutionListener.setUpRequestContextIfNecessary(ServletTestExecutionListener.java:200)
	at org.springframework.test.context.web.ServletTestExecutionListener.prepareTestInstance(ServletTestExecutionListener.java:139)
	at org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:260)
	at org.springframework.test.context.junit.jupiter.SpringExtension.postProcessTestInstance(SpringExtension.java:205)
	at java.base/java.util.stream.ForEachOps$ForEachOp$OfRef.accept(ForEachOps.java:184)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1708)
	at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509)
	at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499)
	at java.base/java.util.stream.ForEachOps$ForEachOp.evaluateSequential(ForEachOps.java:151)
	at java.base/java.util.stream.ForEachOps$ForEachOp$OfRef.evaluateSequential(ForEachOps.java:174)
	at java.base/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:234)
	at java.base/java.util.stream.ReferencePipeline.forEach(ReferencePipeline.java:596)
	at java.base/java.util.Optional.orElseGet(Optional.java:364)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1596)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1596)
Caused by: java.lang.IllegalArgumentException: Could not find class [org.springframework.boot.web.client.RestTemplateBuilder]
	at org.springframework.util.ClassUtils.resolveClassName(ClassUtils.java:353)
	at org.springframework.core.annotation.TypeMappedAnnotation.adapt(TypeMappedAnnotation.java:451)
	at org.springframework.core.annotation.TypeMappedAnnotation.getValue(TypeMappedAnnotation.java:384)
	at org.springframework.core.annotation.TypeMappedAnnotation.asMap(TypeMappedAnnotation.java:273)
	at org.springframework.core.annotation.AbstractMergedAnnotation.asAnnotationAttributes(AbstractMergedAnnotation.java:191)
	at org.springframework.context.annotation.AnnotationBeanNameGenerator.determineBeanNameFromAnnotation(AnnotationBeanNameGenerator.java:143)
	at org.springframework.context.annotation.AnnotationBeanNameGenerator.generateBeanName(AnnotationBeanNameGenerator.java:110)
	at org.springframework.context.annotation.ConfigurationClassBeanDefinitionReader.registerBeanDefinitionForImportedConfigurationClass(ConfigurationClassBeanDefinitionReader.java:168)
	... 41 more
Caused by: java.lang.ClassNotFoundException: org.springframework.boot.web.client.RestTemplateBuilder
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:526)
	at java.base/java.lang.Class.forName0(Native Method)
	at java.base/java.lang.Class.forName(Class.java:536)
	at java.base/java.lang.Class.forName(Class.java:515)
	at org.springframework.util.ClassUtils.forName(ClassUtils.java:302)
	at org.springframework.util.ClassUtils.resolveClassName(ClassUtils.java:343)
	... 48 more

