# <img src="http://code.google.com/p/wro4j/logo"> Web Resource Optimizer for Java
[![Join the chat at https://gitter.im/wro4j/wro4j](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/wro4j/wro4j?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://api.travis-ci.org/wro4j/wro4j.svg)](http://travis-ci.org/wro4j/wro4j)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/ro.isdc.wro4j/wro4j-core/badge.svg)](https://maven-badges.herokuapp.com/maven-central/ro.isdc.wro4j/wro4j-core)


wro4j is a free and Open Source Java project which will help you to [easily improve](http://wro4j.github.com/wro4j) your web application page loading time. It can help you to keep your static resources (js & css) [well organized](http://wro4j.readthedocs.org/en/stable/WroFileFormat), merge & minify them at [run-time](http://wro4j.readthedocs.org/en/stable/Installation) (using a simple filter) or [build-time](http://wro4j.readthedocs.org/en/stable/MavenPlugin) (using maven plugin) and has a [dozen of features](http://wro4j.readthedocs.org/en/stable/Features) you may find useful when dealing with web resources.


# Getting Started

In order to get started with wro4j, you have to follow only 3 simple steps.

## Compile the project
'''
mvn clean install -DskipTests
''' 

## Step 1: Add WroFilter to web.xml
```xml
<filter>
	<filter-name>WebResourceOptimizer</filter-name>
	<filter-class>ro.isdc.wro.http.WroFilter</filter-class>
</filter>
		 
<filter-mapping>
	<filter-name>WebResourceOptimizer</filter-name>
	<url-pattern>/wro/*</url-pattern>
</filter-mapping>
```		
## Step 2: Create wro.xml
```xml
<groups xmlns="http://www.isdc.ro/wro">
	<group name="all">
		<css>/asset/*.css</css>
		<js>/asset/*.js</js>
	</group>
</groups> 		
```
## Step 3: Use optimized resources
```html
<html>
  <head>
	<title>Web Page using wro4j</title>
	<link rel="stylesheet" type="text/css" href="/wro/all.css" />
	<script type="text/javascript" src="/wro/all.js"/>
  </head>
<body>

</body>
</html>		
```
		
# Documentation

The documentation for this project is located [here](http://wro4j.readthedocs.org/en/stable/)


# Issues

Found a bug? Report it to the [issue tracker](https://github.com/wro4j/wro4j/issues)


# Feedback

If you have any questions or suggestions, please feel free to post a comment to the [discussion group](https://groups.google.com/forum/#!forum/wro4j)

[Follow me](http://twitter.com/#!/wro4j) on Twitter.


# License

This project is available under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).
