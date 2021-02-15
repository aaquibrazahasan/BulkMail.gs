function sentMail(){
  var password = 2;
  var email = 1;
  
    
  var emailTemp = HtmlService.createTemplateFromFile("Email.html");
  var ws = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Customer List");
  var wsSettings = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Settings");
  var name = wsSettings.getRange("B2").getValue();
  var subject = wsSettings.getRange("B1").getValue();
  var data = ws.getRange("A2:C" + ws.getLastRow()).getValues();
  var QuotaLeft = MailApp.getRemainingDailyQuota();
  Browser.msgBox(QuotaLeft);

  data.forEach(function(row){
  
  emailTemp.un = row[email];
  emailTemp.ps = row[password];
  
  
  var htmlMessage = emailTemp.evaluate().getContent();
  
  MailApp.sendEmail(
   
  row[email],
  subject,
  "You email doesn't support HTML,",
  {name:name,htmlBody:htmlMessage}
  
  ); 
  
  
  });

}
