# Log4J_for_JAVA_DEVELOPERS
THIS IS FOR JAV DEVS Log4J
```java


        					Written in Java and powered by Apache Foundation.
					
								Need for logging tool.
								
We use system.out.printin to print the flow of the program onto the console during the
runtime enviroment.

System.out.printin is often termed as heavy weight, it is because of its synchronized
method. this makes it expensive and time consuming.

At the time of production, we can neither use System.out-printin nor debugging tool.

We could use debugging tool to look for any issues. But in case of remote
envirmonment debugging becomes tougher as debugging tool are not meant to work
for remote systems.

Log4j comes as a solution that could solve the above problems making the developers
life easier.


                            WHAT IS Log4J
            To track the flow of application and to maintan a record of the overall
              process we go for LOG4j framework.
             - Highly configurable
             - Logging is highly flexible and could be set to various levels
        

                                 LOG4J MAIN COMPONENTS

                    LOGGER          APPENDER            LAYOUT

                    LOGGER: To Registe the class to the LOGGER
                    APPENDER: To append the logging information to the respective destination.
                    LAYOUT: Styling the logging information.




                                    LOG4J FEATURES
                Thread safe
                High speed optimization due to tracing capability
                multiple appenders support
                Support I18N-Internationalzation
                Customized configuring
                .xml/.properties way of configuration
                Various level logging
                Customized formatting of the log messages using layout class
                it is fail stop



                            ADVANTAGES OF LOG4J 

                Quick debugging
                Easy maintenance
                Structured storage
        
                            DISADVANTAGES

                It slows down application
                Scrolling blindness due to configuaration file beign to verbose

```


# Introduction of java logging:
```java
									 Log4J
									 
									 
			Environment:  System where applications is running with all setup.
			
					Types of env:
						1) Dev env, 2) QA env 3) UAT env ( User Accetpetnce Test) 4) Production env
			 
			 log4j components

			  logger 
			  appender 
			  layout
			  
			  
			  logger object
					this object must be created inside class for which log4j is required
					Ex: controllers, sevices. repository, ryv nrrfd loh4j servers
					if we get any exception/errors inside these classes 
					we can trace those into log file.
					
					DO NOT CREATE logger object if we dont want to logging for classs
						Ex: model/entity
						
				object 
				private static Logger log = Logger.getLogger(className.class);
				  
						
						
						
						
				Appender:
						Appender is used to specify where to store Log message.
						
						
				Types of Appenders
						a consoleAppender   : print log message on consoleAppender
						b fileAppender      : stroe log message in .log file
						c JdbcAppender      : store log message inside database table
						d ftp/telnetAppender : send data from one server to another server
						e SMTP Appender     : send log message using email.
						
				LAYOUT: It indicates message format that should be printed on appender
						1 simple layout L print message as it is given by applications
						2 HTML LAYOUT : PRINT MESSAGE AS HTML file
						3 XML layout : print message as XML output
						4 pattern layout : print message as given opattern by programmer
						
						
		
		
		Priority methods
		
						these are pre-defined methods given inside logger object
						by usign these methods, we have to print messages at appender
						
		    
			
			slno	    NAME 	    METHOD
			1 		DEBUG	debug(msg)
			2 		INFO	info (msg)
			3 		WARN	warn(msg)
			4		ERROR	error(msg)
			5		FATAL   fatal(msg)
			
			
			
			
			
			DEBUG : This method is use dto print a final/success message.
			Ex: employee created with ID-EMP-689900 successfully
			  
			  
			 INFO: this method is used to print current status in execution
			 ex: request cam to controller methodobject sent to service layer
			 service returned back to controller
			 try block execution completed
			 
			 
			WARN : this method is used to pritn warnings in applications
			Ex: file object  is created but never closed
			    variable is created, but not used
				
			ERROR : this mthod is used to print any general exception/errors
						Ex: NullPointerException, arrayIndexOutofBoundsExcepton
						apps id is null can not be processed
						
			FATAL : this method is used to print any high level exception 
						application is stoped not working condition right now 
					

first logger code

			in main method
			
				Public static Logger log = new Logger.getLogger(ClassName.class);
			     public static void main(String[] args){
								// 1 CREATE layout
								
								Layout layout = new SimpleLayout();
								
								// 2 create appender  + linked with layout
								
								Appender app = new consoleAppender(layout);
								
								// 3 link appender with logger
								
								log.addAppender(app);
								
								
								
								//------------- print message
								log.info("from info");
								log.debug("from debug")
								log.fatal("from fatal");
								log.error("from error");
								log.warn("from warn");
								
								
								}
```


# Patterns 
```java


            %C upperCase %C mean current class printing
            %M upperCase %M mean current method name printing
            %m lowerCase %m mean message
            %p lowerCase priority method name 
            %L upperCase Line number printing
            %l lowercase line number with link
            %n lowercase new line or next line
            %r lowercase time in milli sec
            %% to print one % symbol
            we can also use extra symbols like alphaNumrics and spiceal char's




```

# Date and time patterns
```java
Date & Time patterns


     %d lowerCase date and time

     %d (dd-mmm-yy- hh:mm:ss)




```

# Real world example for log4J concept  log4j.propertites


```java
     RootLogger Following levels
                    debug DEBUG
                    info  INFO
                    warn  WARN
                    error ERROR
                    fatal FATAL
            IF WE TAKE DEBUG --- DEBUG TO FATAL PRINT EVERYTHING


 every line start with log4j._____ only
 # Root logger
 log4j.rootLogger=DEGUG,sout,myFile  # use only upperCase chars 'sout is the name like variable'

 # Appender + layout details
 log4j.appender.sout = org.apache.log4j.consoleAppender
 log4j.appender.sout.Target=System.out
 log4j.appender.sout.layout= org.apache.log4j.PatternLayout
 log4j.appender.sout.layout.conversionPattern= %d{yy-MM-dd hh:mm} %p %C %m %M %n 



   # comments

   # we can create file  in local machine by using FILE APPENDER 

        log4j.appender.myFile=org.apache.log4j.FileAppender
        log4j.appender.myFile.File=D:/mylogs.log
        log4j.appender.myFile.layout=org.apache.log4j.PatternLayout
        log4j.appender.myFile.layout.ConvesionPattern=%d{yy-MM-dd hh:mm} %p :%C %m %M %n





    # im working with database 
         
```
