Scripts for deployment of WebObjects/Wonder app on Wildfly 10

1. Place the text in 'servletDeployment=true' in the wolips.properties file, located in ~/Library/Application Support/WOLips
2. Replace ERXApplication with ERXServletApplication
3. Change in build.properties file: webXML=true
4. WOLips tools ant build: select sssd and war
5. Deploy war on wildfly
6. Make sure that is doesn't load with an ERROR otherwise the class loading is aborted (e.g. due to tlds)
    From the generated WAR archive remove the tlds in WEB-INF/tlds and in WEB-INF/app.woa/Contents/Frameworks/JavaWOJSPServlet.framework/Resources
7. Add LICENSE file in your project directory with key from /System/Library/JavaWebObjects.framework/Resources/License.key
8. Deploy on Wildfly 10 via the interface. In the server.log you should see WebObjects startup
9. Your applications is shown in localhost:8080/<war file>/WebObjects/<war file>.woa

There is a bug in the ant script, the war ends up in the directory ${dest.dir}
