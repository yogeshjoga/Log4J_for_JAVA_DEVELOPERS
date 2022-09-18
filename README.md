# Log4J_for_JAVA_DEVELOPERS
THIS IS FOR JAV DEVS Log4J


# Introduction of java logging:\
```java
									 Log4J
									 
									 
			Environment:  System where applications is running with all setup.
			
					Types of env's:
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
						
						
		##########################################################################################################
		
		Priority methods
		
						these are pre-defined methods given inside logger object
						by usign these methods, we have to print messages at appender
						
		    
			
			slno	NAME 	METHOD
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
						
			
			






*******************************************************************


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



























