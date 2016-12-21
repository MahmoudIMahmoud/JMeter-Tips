#How to read configuration files (.properties format) inside jmeter?
##Here is how?
1. Add a "BeanShell" sampler to your plan.
2. Past the folowing code in the script Area.

```Java
import org.apache.jmeter.services.FileServer;
log.info("======================");
currentPath=FileServer.getFileServer().getBaseDir();
vars.put("current.path",currentPath);
log.info(FileServer.getFileServer().getBaseDir());

myprop = new Properties();
myprop.load(new FileInputStream(currentPath+"/Configs.properties"));

names=myprop.stringPropertyNames();
for(String name : names){
	vars.put(name,myprop.getProperty(name));
	log.info(name);
}
```

3.The file containing the confiogurations named "Configs.properties", and it is in the same folder as the .JMX paln file.
###The properties file formate is just like:
property name = property value

###Note:
It is recommended to put that sampler in a run once controller.
