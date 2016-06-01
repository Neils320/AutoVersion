# AutoVersion
Android Studio�Զ����ɰ�׿versionCode��versionName
*Read this in other languages: [English](README.md), [��������](README.zh-cn.md).*

### ʹ�÷���
####1 ��� gradle **buildscript** ����
��project��build.gradle�ļ���
```groovy
buildscript {
	...
    dependencies {
        classpath 'com.nillith.android:autoversion:1.0.1' // ���������autoversion����
    }
}
```
####2 ���Android Studio��Sync Project With Gradle Files ��ť
####3 ����android config��
��Module����build.gradle�ļ���
```groovy
import com.nillith.android.tools.build.version.AutoVersion // ����
apply plugin: 'com.android.application'

AutoVersion.setVersionNumber(1, 0, 0) // �ֱ���app��major��minor��patch�汾��(autoversionֻ�Զ�����build�汾��)

android {
...
    defaultConfig {
        ...
        versionCode AutoVersion.versionCode // ����versionCode
        versionName AutoVersion.versionName // ����versionName, ��ͬ��"$major.$minor.$patch.$versionCode"
		...
    }
	...
}
```
