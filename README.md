# nyla-email
Emails (POP3, SMTP, IMAP) send/receive wrapper APIs using JavaMail


# Configuration

This module using the NYLA [Config](https://github.com/nyla-solutions/nyla/blob/master/src/main/java/nyla/solutions/core/util/Cryption.java) object. It supports setting the following properties from config.properties, or Java System Properties or Environment variables. 
	
	
	#Mail Server
	mail.host=smtp.office365.com
	
	@Flag whether the from user/password is needed
	mail.auth.required=true
	
	#EMail from user
	mail.from=imani@home.org
	
	
	#Mail User password using Nyla Cryption
	mail.from.password={cryption}HMlC6NiiCErfg3KTYXjktA==
	
	# Mail SMTP port
	mail.smtp.port=587
	
	# Mail email Default port
	mail.port=587
	
	# Whether SSL is required
	mail.smtp.ssl.enable=false
	
	# Whether TLS encryption is used
	mail.smtp.starttls.enable=true
	

## Send Mail Usage 

		String to = "green_gregory@yahoo.com";
		String subject = "Test";
		String messageBody = "<b>Hello World</b>";
		
		Email email = new Email();
		email.setMailFromUser(Config.getProperty("junit.from.user"));
		email.sendMail(to, subject, messageBody);
		
## Read Mail Usage

		Email email = new Email();
		int count = 10;
		int startIndex = 1;
		String subjectPattern = ".*";
		
		Collection<EmailMessage> results = email.readMatches(count, startIndex, subjectPattern);
		
		for (EmailMessage message : results)
		{
			System.out.println("message:"+message);
		}