function doGet(request){
 // Change Spread Sheet url
 var bookingname = request.parameter.bookingname
 var startdate = request.parameter.datetime+'+07:00'
 var hours = request.parameter.duration
 var title = request.parameter.title
 createEvent(bookingname,startdate,hours,title)
 var result = {}
 result.result = 'added'
//  console.log(result)
 var result = JSON.stringify(result);
 return ContentService.createTextOutput(result).setMimeType(ContentService.MimeType.JSON); 
}



function createEvent(bookingname,sdate,hours,title) {


  var calendarId = 'primary';
  var startdate = new Date(sdate).toISOString()
  var enddate = new Date(sdate)

  enddate = new Date(enddate.getTime() + 60*hours*60000);
  enddate = enddate.toISOString()

  //enddate = enddate.addHours(hours).toISOString()

  console.log(startdate)
  console.log(enddate)
  var event = {
    summary: bookingname,
    //location: '',
    description: title,
    start: {
      dateTime: startdate
    },
    end: {
      dateTime: enddate
    },
    colorId: 11
  };
  event = Calendar.Events.insert(event, calendarId);
  console.log('Event ID: ' + event.id);
}
