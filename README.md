Quercus
=======

# Quercusとは

PHPをJVM上で実行するためのミドルウェアです。詳しくは本家を参照ください。http://quercus.caucho.com/

# 改変内容
本家の Quercus 4.0.39 を JDK7 でビルドできるようにしたものです。
ライセンスは本家のGPLをそのまま継承しています。

# ビルド方法
## ビルド環境
- JDK7(JDK8ではビルドできません)
- Maven2以降

## ビルド方法

    $ mvn clean package

targetディレクトリにquercus-VERSION.jarが生成されます。

## デプロイ方法

    $ mvn clean deploy
    $ git add repos
    $ git commit repos -m '....'
    $ git push origin master

# サンプルプロジェクト

https://github.com/dwango/quercus-sample

# Mavenプロジェクトで利用する方法
pom.xmlに以下のようにリポジトリとjarへの依存関係を追加する。

    <repositories>
        // ...
        <repository>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
            <id>dwango-quercus-repos</id>
            <name>Dwango Quercus Repository</name>
            <url>https://raw.github.com/dwango/quercus/master/repos/</url>
        </repository>
        //...
    </repositories>
    // ...
    <dependencies>
        // ...
        <dependency>
            <groupId>com.caucho</groupId>
            <artifactId>quercus</artifactId>
            <version>4.0.39</version>
        </dependency>
        // ...
    </dependencies>