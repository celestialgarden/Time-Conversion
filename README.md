# Time-Conversion
import time
from datetime import datetime
import pytz

def convert_datetime_timezone(dt, tz1, tz2):
    #define the two time zone in standard format in pytz
    tz1 = pytz.timezone(tz1)
    tz2 = pytz.timezone(tz2)

    # convert time into standard format
    dt = datetime.strptime(dt, "%H:%M")

    #get enter_timezone's time
    dt = tz1.localize(dt)

    #convert it into output time zone
    dt = dt.astimezone(tz2)
    # convert time into standard format
    dt = dt.strftime("%H:%M")

    return dt

def convert(input_zone, input_time, output_zone):
    i=0
    
print( "Please Enter Input Time Zone: US/Alaska, Central, Eastern, Hawaii, Mountain, Pacific" )
start_zone = raw_input()

print( "Please Enter Time: e.g., 10:00, 13:00" )
start_time = raw_input()

print( "Please Enter Input Time Zone: US/Alaska, Central, Eastern, Hawaii, Mountain, Pacific" )
end_zone = raw_input()

end_Time = conver_datetime_timezone( start_time, start_zone, end_zone )
print( "Output Time:" + end_time )
