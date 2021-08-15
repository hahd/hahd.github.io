//contact form JavaScript
$(document).ready(function (){ //function
    $('.send').click(function (event){ //function
       event.preventDefault(); //not allowing users to click send with empty text boxes
        
       //declaring and initializing variables
       var message = $('.messageBox').val();
       var email = $('.emailBox').val();
       var name = $('.nameBox').val();
       var status = $('.status');
       status.empty(); //won't print out a status message
 
       //email validation if/else statement
       if(email.length > 5 && email.includes('@') && email.includes('.')){
          status.append('<div>Email is valid</div>');
       }
       else {
          event.preventDefault(); //preventing users from clicking send when email is invalid or email box is empty
          status.append('<div>Email is invalid</div>')
       }
 
       //message validation if/else statement
       if(message.length >= 10) {
          status.append('<div>Message is valid</div>')
       }
       else {
          event.preventDefault(); 
          status.append('<div>Message is too short</div>')
       }
 
       //full name validation if/else statement
       if(name.length > 3 && name.includes(' ')){
          status.append('<div>Full name is valid</div>')
       }
       else{
          event.preventDefault(); 
          status.append('<div>Full name is invalid</div>')
       }
    })
 })