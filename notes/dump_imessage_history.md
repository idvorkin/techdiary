## Accessing iMessage history

iMessage is just a sqllite file located @

    ~/Library/Messages/chat.db

A nice sqllite cli is litecli (pip install litecli)

    litecli  -e'select  text, date, is_from_me , destination_caller_id, h.id from message m, handle h where m.handle_id = h.ROWID  limit 200 ' chat.db

Dates are in a goofy formab, handle them

    litecli  -e'select  text, datetime(date/1000000000 + strftime("%s", "2001-01-01") ,"unixepoch","localtime")  as date_uct , is_from_me , destination_caller_id, h.id from message m, handle h where m.handle_id = h.ROWID  limit 10 ' chat.db | tee o1

References:

- iMessage Analyis in pandas: https://github.com/yortos/imessage-analysis
- python example: https://github.com/mattrajca/pymessage-lite/blob/master/imessage.py
