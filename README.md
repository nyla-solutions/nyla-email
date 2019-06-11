# nyla-email
Emails (POP3, SMTP, IMAP) send/receive wrapper APIs using JavaMail



## Usage 

		String to = "green_gregory@yahoo.com";
		String subject = "Test";
		String messageBody = "<b>Hello World</b>";
		
		Email email = new Email();
		email.setMailFromUser(Config.getProperty("junit.from.user"));
		email.sendMail(to, subject, messageBody);