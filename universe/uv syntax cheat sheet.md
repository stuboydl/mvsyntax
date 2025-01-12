# Rocket UniVerse (U2) mvbasic cheat sheet

Scraped from the UV Basic Commands Ref v11.4.1 Aug 2023 [UNV-1141-BASR-1]

Keywords are case insensitive eg ACTIVATEKEY = ActivateKey = activatekey

## Operators

### Arithmetic Operators

~~~ mvbasic
expression + expression
expression - expression
expression * expression
expression / expression
expression ^ expression  ;* (**)
~~~

### Assignment Operators

~~~ mvbasic
variable = expression
variable += expression
variable -= expression
variable := expression
~~~

### Logical Operators

~~~ mvbasic
expression AND expression ;* (&)
expression OR expression  ;* (!)
NOT(expression)
~~~

### Pattern Matching Operators

~~~ mvbasic
expression MATCH pattern  ;* MATCHES
~~~

### Relational Operators

~~~ mvbasic
expression = expression  ;* (EQ)
expression # expression  ;* (NE,<>,><)
expression < expression  ;* (LT)
expression > expression  ;* (GT)
expression <= expression ;* (LE,=<,#>)
expression >= expression ;* (GE,=>,#<)
~~~

### String Operators

~~~ mvbasic
expression : expression
expression[ [start,] length]
expression[ delimiter, occurrence, fields] ;* FIELD(delimiter, occurrence, fields)
~~~

### Dynamic Array Operators (aka vector operators)

~~~ mvbasic
ADDS(exp1, exp2)
ANDS(exp1, exp2)
CATS(exp1, exp2)
DIVS(exp1, exp2)
EQS(exp1, exp2)
FIELDS(exp1, p1, p2, p3)
GES(exp1, exp2)
GTS(exp1, exp2)
IFS(exp1, exp2, m3)
LES(exp1, exp2)
LTS(exp1, exp2)
MULS(exp1, exp1)
NES(exp1, exp2)
NOTS(exp1)
ORS(exp1, exp2)
SUBS(exp1, exp2)
~~~

## Statements and Functions

~~~ mvbasic
! [comment.text]
#INCLUDE [filename] program
#INCLUDE program FROM filename
$* [comment.text]
$CHAIN [filename] program
$COPYRIGHT "copyright.notice"
$DEFINE identifier [replacement.text]
$EJECT
$IFDEF identifier [statements] [[$ELSE] [statements]] $ENDIF
$IFNDEF identifier [statements] [[$ELSE] [statements]] $ENDIF
$INCLUDE [filename] program
$INCLUDE program FROM filename
$INSERT primos.pathname
$MAP mapname
$OPTIONS [flavor] [options] ;*(PICK,INFORMATION,REALITY,IN2,DEFAULT,PIOPEN)
$UNDEFINE identifier
* [comment.text]
dynamic.array< field# [ ,value# [,subvalue#]] >
@(column [,row])
@(–code [,arg ])
ABORT [expression …]
ABORTE [expression …]
ABORTM [expression …]
ABS(expression)
ABSS(dynamic.array)
acceptConnection(svr_socket, blocking_mode, timeout, in_addr, in_name, socket_handle)
ACOS(expression)
ACTIVATEKEY key.id, password [ON hostname]
addAuthenticationRule(context, ServerOrClient, Rule, RuleString)
addCertificate(certPath, usedAs, format, algorithm, context, p12pass)
addRequestParameter(request_handle, parameter_name, parameter_value, content_handling)
ADDS(array1, array2)
ALPHA(expression)
amInitialize(hSession, appName, policyName, reasonCode)
amReceiveMsg(hSession, receiverName, policyName, selMsgName, maxMsgLen,dataLen, data, rcvMsgName, reasonCode[,recMsgOption])
amReceiveRequest(hSession, receiverName, policyName, maxMsgLen,dataLen, data, rcvMsgName, senderName, reasonCode [,recReqOption])
amSendMsg(hSession, senderName, policyName, data, sndMsgName,reasonCode)
amSendRequest(hSession, senderName, policyName, responseName, data,sndMsgName, reasonCode)
amSendResponse(hSession, senderName, policyName, rcvMsgName, data,sndMsgName, reasonCode)
amTerminate(hSession, policyName, reasonCode)
analyzeCertificate(cert, format, result, p12pass)
ANDS(array1, array2)
ASCII(expression)
ASIN(expression)
ASSIGNED(variable)
ATAN(expression)
AuditLog(Originator, Action, File, Record, Info, Status, {OldData},{NewData})
AUTHORIZATION "username"
AUXMAP { ON | OFF | expression }
BEGIN CASE
   CASE expression ...
   END CASE
BEGIN TRANSACTION [ISOLATION LEVEL level] ;*(0:NO.ISOLATION,1:READ.UNCOMMITTED,2:READ.COMMITTED,3:REPEATABLE.READ,4:SERIALIZABLE)
   [statements]  { COMMIT [WORK] | ROLLBACK [WORK] }
   [statements]  [{ COMMIT [WORK] | ROLLBACK [WORK] }
   [statements]  ...
   END TRANSACTION
BITAND(expression1, expression2)
BITNOT(expression [,bit#])
BITOR(expression1, expression2)
BITRESET(expression, bit#)
BITSET(expression, bit#)
BITTEST(expression, bit#)
BITXOR(expression1, expression2)
BREAK [KEY] { ON | OFF | expression }
BSCAN ID.variable [, rec.variable] [FROM file.variable [, record]] [USING indexname] [RESET] [BY seq] {THEN statements [ELSE statements] | ELSE statements}
BYTE(expression)
BYTELEN(expression)
BYTETYPE(value)
BYTEVAL(expression [, n] )
CALL name [([MAT] argument [, [MAT] argument …])]
CATS(array1, array2)
CENTURY.PIVOT(year | nn )
CHAIN command
CHANGE(expression, substring, replacement [,occurrence [,begin]] )
CHAR(expression)
CHARS(dynamic.array)
CHECKSUM(string)
CLEAR [COMMON]
CLEARCOMMON [/common.label/]
CLEARDATA
CLEARFILE [file.variable] [ON ERROR statements] [LOCKED statements]
CLEARPROMPTS
CLEARSELECT [ALL | list.variable]
CLOSE [file.variable] [ON ERROR statements]
CLOSESEQ file.variable [ON ERROR statements]
closeSocket(socket_handle)
COL1()
COL2()
COMMAND.EDITOR [{ON | OFF} [INSERT | OVERLAY] [VERBS | ALL] “prompt”}]
COMMIT [WORK] [THEN statements] [ELSE statements ]
COM [/name/] variable [,variable …]
COMMON [/name/] variable [,variable …]
COMPARE(string1, string2  [, justification])
CONVERT(expression1, expression2, variable)
CONVERT expression1 TO expression2 IN variable
COS(expression)
COSH(expression)
COUNT(string, substring)
COUNTS(dynamic.array, substring)
CREATE file.variable {THEN statements [ELSE statements] | ELSE
createCertificate(action, req, signKey, keyPass, CAcert, days, extensions, certOut, signAlg)
createCertRequest(key, inFormat, keyLoc, algorithm, digest, passPhrase, subjectData, outFile, outFormat)
createRequest(URL, http_method, request_handle)
createSecureRequest(URL, http_method, request_handle, security_context)
createSecurityContext(context, “protocol version:[rule],...”)
CRT [print.list]
DATA expression [,expression …]
DATE()
DATETIMEL()
DATETIMEZ()
DBTOXML(xml_document, doc_location, u2xmap_file, u2xmap_location, condition, status)
DCOUNT(string, delimiter)
DEACTIVATEKEY key.id, password [ON hostname]
DEBUG
DEFFUN function [([MAT] argument [, [MAT] argument …] )]
DEL dynamic.array< field# [,value# [,subvalue#]] >
DELETE(dynamic.array, field#[,value#[,subvalue#] ] )
DELETE [file.variable ,] record.ID [ON ERROR statements] [LOCKED statements ] [THEN statements ] [ELSE statements ]
DELETEU [file.variable ,] record.ID [ON ERROR statements] [LOCKED statements ] [THEN statements ] [ELSE statements ]
DELETELIST listname
DESCRINFO(key, variable)
DIGEST(algorithm, data, dataLoc, result)
DIM matrix (rows, columns) [, matrix (rows, columns) …]
DIMENSION matrix (rows, columns) [, matrix (rows, columns) …]
DIM vector (subscript) [, vector (subscript) …]
DIMENSION vector (subscript) [, vector (subscript) …]
DISABLEDEC filename [, multilevel-filename], {ALL |field_list} [ON ERROR statements]
DISPLAY [print.list]
DIV(dividend, divisor)
DIVS(array1, array2)
DOWNCASE(expression)
DQUOTE(expression)
DTX(number [,size] )
EBCDIC(expression)
ECHO {ON | OFF | expression}
ENABLEDEC filename [, multilevel-filename], { ALL |field_list} [ON ERROR statements]
ENCODE(algorithm, action, data, dataLoc, result, resultLoc)
ENCRYPT(algorithm, action, data, dataLoc,key, keyLoc, keyAction, salt, IV, result, resultLoc)
END
ENTER subroutine
ENTER @variable
EOF(ARG.)
EQS(array1, array2)
EQU symbol TO expression [,symbol TO expression …]
EQUATE symbol TO expression [,symbol TO expression …]
EQU symbol LIT[ERALLY] string [,symbol LIT string …]
EQUATE symbol LIT[ERALLY] string [,symbol LIT string …]
EREPLACE(expression, substring, replacement [,occurrence [,begin]] )
ERRMSG message.ID [,message.ID …]
EXCHANGE(string, xx, yy)
EXECUTE commands [CAPTURING variable] [PASSLIST [dynamic.array]] [RTNLIST [variable]] [{SETTING | RETURNING} variable]
EXECUTE commands [,IN < expression] [,OUT > variable] [,SELECT[(list)]< dynamic.array] [,SELECT[(list)] > variable],PASSLIST [(dynamic.array)]] [,STATUS  > variable]
EXECUTE commands [ ,//IN. < expression] [,//OUT. > variable] [,//SELECT.[(list)] < dynamic.array] [,//SELECT.[(list)] > variable] [,//PASSLIST.[(dynamic.array)]] [,//STATUS. > variable]
EXIT
EXP(expression)
EXTRACT(dynamic.array, field#[,value# [,subvalue#]] ) 
FADD(number1, number2)
FDIV(number1, number2)
FFIX(number)
FFLT(number)
FIELD(string, delimiter, occurrence [,num.substr] ) (variable [delimiter, occurrence ,num.substr])
FIELDS(dynamic.array, delimiter, occurrence [ ,num.substr] )
FIELDSTORE(string, delimiter, start, n, new.string)
FILEINFO(file.variable , key )
FILELOCK [file.variable] [, lock.type] [ON ERROR statements] [LOCKED statements]
FILEUNLOCK [file.variable] [ON ERROR statements]
FIND element IN dynamic.array [,occurrence] SETTING fmc [,vmc [,smc]] {THEN statements [ELSE statements] | ELSE statements}
FINDSTR substring IN dynamic.array [,occurrence] SETTING fmc [,vmc [,smc]] {THEN statements [ELSE statements] | ELSE statements}
FIX(number [,precision [,mode]] )
FLUSH file.variable {THEN statements [ELSE statements] | ELSE statements}
FMT(expression, format)expressionformat
FMTDP(expression, format [, mapname ] )
FMTS(dynamic.array, format)
FMTSDP(dynamic.array, format [, mapname] )
FMUL(number1, number2)
FOLD(string, length )
FOLDDP(string, length [, mapname ] )
FOOTING [ON print.channel] footing
FOR variable = start TO end [STEP increment] [loop.statements] [CONTINUE | EXIT] {WHILE | UNTIL} expression] [loop.statements] [CONTINUE | EXIT] NEXT [variable]
FORMLIST [variable] [TO list.number] [ON ERROR statements]
FSUB(number1, number2)
FUNCTION [name] [( [MAT] variable [, [MAT] variable …] )]
GCDISTANCE(lat1,lon1,lat2,lon2)
generateKey(privKey, pubKey, format, keyLoc, algorithm, keyLength, passPhrase, paramFile)
generateKey(privKey, pubKey, format, keyLoc, algorithm, keyLength, passPhrase, paramFile)
GES(array1, array2)
GET read.var[, length] [SETTING read.count] FROM device [UNTIL eop.char.list ] [RETURNING last.char.read ] [WAITING seconds ] [THEN statements ] [ELSE statements]
GETX read.var[, length] [SETTING read.count] FROM device [UNTIL eop.char.list ] [RETURNING last.char.read ] [WAITING seconds ] [THEN statements ] [ELSE statements]
getCipherSuite(context,ciphers)
getIpv([networkexpr])
GET(ARG. [,arg#] ) variable [THEN statements] [ELSE statements]
getHTTPDefault(option, value)
GETLIST listname [TO list.number] [SETTING variable] {THEN statements [ELSE statements] | ELSE statements}
GETLOCALE(category)
GETREM(dynamic.array)
getSocketErrorMessage(errCode, errMsg)
getSocketInformation(socket_handle, self_ or_ peer, socket_info)
getSocketMap(aSocket, mapname)
getSocketOptions(socket_handle, options)
GOSUB statement.label [:]
GO SUB statement.label [:]
GO statement.label [:]
GOTO statement.label [:]
GO TO statement.label [:]
GROUP(string, delimiter, occurrence [,num.substr] )
GROUPSTORE new.string IN string USING start, n [ ,delimiter]
GTS(array1, array2)
HEADING [ON print.channel] heading
HEADINGE [ON print.channel] heading
HEADINGN [ON print.channel] heading
hmac= HMAC(hmacAlg, hmacKey, hmacData, [outFormat])
HUSH { ON | OFF | expression} [SETTING status ]
ICHECK(dynamic.array [, file.variable] , key [, column#] )
ICONV(string, conversion)
ICONVS(dynamic.array, conversion)
IF expression {THEN statements [ELSE statements] | ELSE statements}
IFS(dynamic.array, true.array, false.array)
ILPROMPT(in.line.prompt)
INCLUDE [filename] program
INCLUDE program FROM filename
INDEX(string, substring, occurrence)
INDEXS(dynamic.array, substring, occurrence)
INDICES(file.variable [,indexname])
initSecureServerSocket(name_or_IP, port, backlog, svr_socket, context)
initServerSocket(name_or_IP, port, backlog, svr_socket)
INMAT([array] )
INPUT variable [,length] [:] [_]
INPUT @ (col, row) [, | :] variable [,length] [:] [format] [_]
INPUTIF @ (col, row) [, | :] variable [,length] [:] [format] [_] [THEN statements] [ELSE statements]
INPUTCLEAR
INPUTDISP [@(col, row) [, | :]] variable [format]
INPUTDP variable [, length] [:] [_] [THEN statements] [ELSE statements]
INPUTERR [error.message]
INPUTNULL character
INPUTTRAP [trap.chars] {GOTO | GOSUB} label [ ,label …]
INS expression BEFORE dynamic.array< field# [,value# [ ,subvalue#]] >
INSERT(dynamic.array, field#, value#, subvalue#, expression)
INSERT(dynamic.array, field# [ ,value# [,subvalue#]] ; expression)
INT(expression)
ISNULL(variable)
ISNULLS(dynamic.array)
ITYPE(i.type)
KEYEDIT(function, key) [, (function, key)] …
KEYEXIT(value, key) [, (value, key)] …
KEYIN()
KEYTRAP(value, key) [, (value, key)] …
LEFT(string, n)
LEN(string)
LENDP(string [,mapname] )
LENS(dynamic.array)
LENSDP(dynamic.array [, mapname] )
LES(array1, array2)
LET variable = expression
LN(expression)
loadSecurityContext(context, name, passPhrase)
LOCALEINFO(category)
LOCATE expression IN dynamic.array[< field# [, value#] >] [, start] [BY seq] SETTING variable {THEN statements [ELSE statements] | ELSE statements}
LOCATE expression IN dynamic.array<field# [, value#  [, subvalue#]] >  [BY seq] SETTING variable    {THEN statements [ELSE statements] | ELSE statements}
LOCATE(expression, dynamic.array [, field# [, value#]] ; variable [;seq] )  { THEN statements [ELSE statements] | ELSE statements }
LOCK expression [THEN statements] [ELSE statements]
LOOP [CONTINUE | EXIT] [{WHILE | UNTIL} expression [DO]] [loop.statements] [CONTINUE | EXIT] REPEAT
LOWER(expression)
LTS(array1, array2)
MAT array = expression
MAT array1 = MAT array2
MATBUILD dynamic.array FROM array [,start [,end]] [USING delimiter]
MATCHFIELD(string, pattern, field)
MATPARSE array FROM dynamic.array [,delimiter]
MATPARSE array [,start [,end]] FROM dynamic.array [USING delimiter] [SETTING elements]
MATREAD array FROM [file.variable,] record.ID [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
MATREADL array FROM [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
MATREADU array FROM [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
MATWRITE array ON | TO [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
MATWRITEU array ON | TO [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
MAXIMUM(dynamic.array)
MINIMUM(dynamic.array)
MOD(dividend, divisor)
MODS(array1, array2)
MQCLOSE(hConn, hObj, options)
MQCONN(qManager, hConn)
MQDISC(hConn)
MULS(array1, array2)
NAP [milliseconds]
NEG(number)
NEGS(dynamic.array)
NES(array1, array2)
NEXT [variable]
NOBUF file.variable {THEN statements [ELSE statements] | ELSE statements}
NOT(expression)
NOTS(dynamic.array)
NOW()
NULL
NUM(expression)
NUMS(dynamic.array)
OCONV(string, conversion)
OCONVS(dynamic.array, conversion)
ON expression GOSUB statement.label [:] [,statement.label [:]… ]
ON expression GO[TO] statement.label [:] [,statement.label [:] … ]
OPEN [dict,] filename [TO file.variable] [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
OPENCHECK [dict,] filename [TO file.variable] {THEN statements [ELSE statements] | ELSE statements}
OPENDEV device TO file.variable [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
OPENPATH pathname [TO file.variable] [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
OPENSEQ filename, record.ID TO file.variable [USING dynamic.array] [ON ERROR statements] [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
OPENSEQ pathname TO file.variable [USING dynamic.array] [ON ERROR statements] [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
openSecureSocket(name_or_IP, port, mode, timeout, socket_handle, context)
openSocket(name_or_IP, port, mode, timeout, socket_handle)
OpenXMLData(xml_handle,xml_data_extraction_rule, xml_data_handle)
ORS(array1, array2)
PAGE [ON print.channel] [page#]
PERFORM command
PRECISION expression
PrepareXML(xml_file,xml_handle)
PRINT [ON print.channel] [print.list]
PRINTER { ON | OFF | RESET }
PRINTER CLOSE [ON print.channel]
PRINTERR [error.message]
PROCREAD variable {THEN statements [ELSE statements] | ELSE statements}
PROCWRITE string
PROG [name]
PROGRAM [name]
PROMPT character
protocolLogging(log_file, log_action, log_level)
PWR(expression, power)
PyCall(PyCallableObject[,arg1, arg2, ...])
PyCallFunction(moduleName, functionName[, arg1, arg2, ...])
PyCallMethod(pyobject, methodName [,arg1, arg2, ...]
PyGetAttr(pyobject, attrName)
PyImport(moduleName)
PySetAttr(pyobject, attrName, value)
QUOTE(expression)
RAISE(expression)
RANDOMIZE [(expression)]
READ  dynamic.array  FROM [file.variable,] record.ID [ON ERROR  statements] { THEN  statements [ELSE  statements] | ELSE  statements } 
READ{L|U} dynamic.array FROM [file.variable ,] record.ID [ON ERROR  statements] [LOCKED  statements] { THEN  statements [ELSE  statements] | ELSE  statements } 
READV dynamic.array FROM [file.variable ,] record.ID ,  field# [ON ERROR  statements] { THEN  statements [ELSE  statements] | ELSE  statements } 
READV{L|U} dynamic.array  FROM [file.variable ,] record.ID , field# [ON ERROR  statements] [LOCKED  statements] { THEN  statements [ELSE  statements] | ELSE  statements } 
READBLK variable FROM file.variable, blocksize THEN statements [ELSE statements] | ELSE statements }
READLIST dynamic.array [FROM list.number] { THEN statements [ELSE statements] | ELSE statements }
READNEXT dynamic.array [,value [,subvalue]] [FROM list] {THEN statements [ELSE statements] | ELSE statements}
READSEQ variable FROM file.variable [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
readSocket(socket_handle, socket_data, max_read_size, time_out, mode, actual_read_size)
READT [UNIT (mtu)] variable {THEN statements [ELSE statements] | ELSE statements}
ReadXMLData(xml_data_handle, rec)
REAL(number)
RECORDLOCKL file.variable , record.ID [ON ERROR statements] [LOCKED statements]
RECORDLOCKU file.variable , record.ID [ON ERROR statements] [LOCKED statements]
RECORDLOCKED(file.variable , record.ID )
RELEASE [file.variable [,record.ID]] [ON ERROR statements]
ReleaseXML(XMLhandle)
REM(dividend, divisor)
REM [comment.text]
REMOVE(dynamic.array, variable)
REMOVE element FROM dynamic.array SETTING variable
REPLACE(expression, field#, value#, subvalue# { , | ; } replacement)
REPLACE(expression [,field# [,value#]] ; replacement)
RETURN [TO statement.label]
RETURN(expression)
REUSE(expression)
REVREMOVE element FROM dynamic.array SETTING variable
REWIND [UNIT (mtu)] {THEN statements [ELSE statements] | ELSE statements}
RIGHT(string, n)
RND(expression)
ROLLBACK [WORK] [THEN statements] [ELSE statements ]
RPC.CALL(connection.ID, procedure, #args, MAT arg.list, #values, MAT return.list)
RPC.CONNECT(host, server)
RPC.DISCONNECT(connection.ID)
saveSecurityContext(context, name, passPhrase)
SADD(string.number.1, string.number.2)
SCMP(string.number.1, string.number.2)
SDIV(string.number.1, string.number.2 [,precision])
SEEK file.variable [, offset [, relto]] {THEN statements [ELSE statements] | ELSE statements}
SEEK(ARG. [,arg#] ) [THEN statements] [ELSE statements]
SELECT [variable] [TO list.number] [ON ERROR statements]
SELECTN [variable] [TO list.number] [ON ERROR statements]
SELECTV [variable] TO list.variable [ON ERROR statements]
SELECTE TO list.variable
SELECTINDEX index [, alt.key] FROM file.variable [TO list.number]
SELECTINFO(list, key)
SEND output [:] TO device { THEN statements [ELSE statements] | ELSE statements }
SENTENCE()
SEQ(expression)
SEQS(dynamic.array)
setAuthenticationDepth(context, depth, ServerOrClient)
setCipherSuite(context,cipherSpecs)
setClientAuthentication(context,option)
setIpv(option[,sockettype])
setPrivateKey(key, format, keyLoc, passPhrase, validate, context, p12pass)
setRandomSeed(inFiles, outFile, length, context)
SET TRANSACTION ISOLATION LEVEL level
setHTTPDefault(option, value)
setRequestHeader(request_handle, header_name, header_value)
SETLOCALE(category, value)
SETREM position ON dynamic.array
setSocketMap(mapname)
setSocketOptions(socket_handle, options)
showSecurityContext(context, config)
SIGNATURE(algorithm, action, data, dataLoc, key, keyLoc, keyFmt, pass, sigIn, result, p12pass)
SIN(expression)
SINH(expression)
SLEEP [seconds | hh:mm[:ss]]
SMUL(string.number.1, string.number.2)
SOAPCreateRequest(URL, soapAction, Request)
SOAPCreateSecureRequest(URL, soapAction, Request, security_context)
SOAPGetDefault(option, value)
SOAPGetFault(respData, soapFault)
SOAPGetResponseHeader(Request, headerName, headerValue)
SOAPSetRequestBody(Request, value)
SOAPSetRequestContent(Request, reqDoc, docTypeFlag)
SOAPSetRequestHeader(Request, value)
SOAPRequestWrite(Request, reqDoc, docTypeFlag)
SOAPSetDefault(option, value)
SOAPSetParameters(Request, URI, serviceName, paramArray)
SOAPSubmitRequest(Request, timeout, respHeaders, respData, soapStatus)
SOUNDEX(expression)
SPACE(expression)
SPACES(dynamic.array)
SPLICE(array1, expression, array2)
SQRT(expression)
SQUOTE(expression )
SSELECT [variable] [TO list.number] [ON ERROR statements]
SSELECTN [variable] [TO list.number] [ON ERROR statements]
SSELECTV [variable] TO list.variable [ON ERROR statements]
SSUB(string.number.1, string.number.2)
STATUS()
STATUS dynamic.array FROM file.variable {THEN statements [ELSE statements] | ELSE statements}
STOP [expression]
STORAGE arg1arg2arg3
STR(string, repeat)
STRS(dynamic.array, repeat)
submitRequest(request_handle, time_out, post_data,response_headers,response_data, http_status)
SUBR(name, [argument [,argument …]] )
SUBROUTINE [name] [([MAT] variable [, [MAT] variable …] )]
SUBS(array1, array2)
SUBSTRINGS(dynamic.array, start, length)
SUM(dynamic.array)
SUMMATION(dynamic.array)
SWAP variable1, variable2
SWAP MAT variable1, MAT variable2
SYSTEM(expression)
TABSTOP expression
TAN(expression)
TANH(expression)
TERMINFO(argument)
TIME()
TIMEDATE()
TIMEOUT {file.variable | link.number}, time
TODATE(datetime)
TODATETIME(date, time)
TOTIME(datetime)
TPARM(terminfo.string, [arg1], [arg2], [arg3], [arg4], [arg5], [arg6], [arg7], [arg8] )
TPRINT [ON print.channel] [print.list]
TRANS([DICT] filename, record.ID, field#, control.code)
TRANSACTION ABORT
TRANSACTION COMMIT {THEN statements [ELSE statements] | ELSE statements}
TRANSACTION START {THEN statements [ELSE statements] | ELSE statements}
TRIM(expression [,character [,option]] )
TRIMB(expression)
TRIMBS(dynamic.array)
TRIMF(expression)
TRIMFS(dynamic.array)
TRIMS(dynamic.array)
TTYCTL file.variable, code# {THEN statements [ELSE statements] | ELSE statements}
TTYGET variable [FROM {file.variable | LPTR [n] | MTU [n] }]TTYGET statement {THEN statements [ELSE statements] | ELSE statements}
TTYSET dynamic.array [ON {file.variable | LPTR [n] | MTU [n] }] {THEN statements [ELSE statements] | ELSE statements}
UDOArrayAppendItem(udoHandle, value)
UDOArrayDeleteItem(udoHandle,index)
UDOArrayGetItem(udoHandle, index, value[out], value_type[out])
UDOArrayGetNextItem(udoHandle, value[out], type[out])
UDOArrayGetSize(udoHandle, size[out])
UDOArrayInsertItem(udoHandle, index, value)
UDOArraySetItem(udoHandle, index, value)
UDOClone(udoHandle, newUdoHandle[out])
UDOCreate(udoType, udoHandle[out])
UDODeleteProperty(udoHandle, name)
UDOFree(udoHandle)
UDOGetLastError(errorCode[out], errorMessage[out])
UDOGetNextProperty(udoHandle, name[out], value[out], value_type[out])
UDOGetOption(option, value[out])
UDOGetProperty(udoHandle, name, value[out], value_type[out])
UDOGetPropertyNames(udoHandle, udoArray[out])
UDOGetType(udoHandle, type[out])
UDOIsTypeOf(udoHandle, type)
UDORead(inputString, inputType, udoHandle[out])
UDOSetOption(option, value)
UDOSetProperty(udoHandle, name, value)
UDOWrite(udoHandle, outputType, outputString[out])
UNASSIGNED(variable)
UNICHAR(unicode)
UNICHARS(dynamic.array)
UNISEQ(expression)
UNISEQS(dynamic.array)
UNLOCK [expression]
UPCASE(expression)
UPRINT [ON print.channel] [print.list ]
USERINFO(code, value, userinfo)
WEOF [UNIT (mtu)] {THEN statements [ELSE statements] | ELSE statements}
WEOFSEQ file.variable [ON ERROR statements]
WRITE expression {ON | TO} [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
WRITEU expression {ON | TO} [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
WRITEV expression {ON | TO} [file.variable,] record.ID, field# [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
WRITEVU expression {ON | TO} [file.variable,] record.ID, field# [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
WRITEBLK expression ON file.variable {THEN statements [ELSE statements] | ELSE statements}
WRITELIST dynamic.array ON listname
WRITESEQ expression {ON | TO} file.variable [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
WRITESEQF expression {ON | TO} file.variable [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
writeSocket(socket_handle, socket_data, time_out, mode, actual_write_size)
WRITET [UNIT (mtu)] variable {THEN statements [ELSE statements] | ELSE statements}
XDOMAddChild(xmlHandle, xpathString, nsMap, nodeHandle, dupFlag,nodeType)
XDOMAppend(xmlHandle, xpathString, nsMap, nodeHandle, dupFlag)
XDOMClone(xmlHandle, newXmlHandle, depth)
XDOMClose(domHandle)
XDOMCreateNode(xmlHandle, nodeName, nodeValue, nodeType, nodeHandle)
XDOMCreateRoot(domHandle)
XDOMEvaluate(xmlHandle, xpathString, nsMap, aValue)
XDOMGetAttribute(nodeHandle, attrName, nodeHandle)
XDOMGetChildNodes(xmlHandle, nodeListHandle)
XDOMGetElementById(xmlHandle,idstr,nodeHandle)
XDOMGetElementsByName(xmlHandle, namestr, nodeListHandle)
XDOMGetElementsByTag(xmlHandle, tagname, nodeListHandle)
XMLGetError(errorCode, errorMessage)
XDOMGetNodeName(nodeHandle, nodeName)
XDOMGetNodeType(nodeHandle, nodeType)
XDOMGetNodeValue(nodeHandle, nodeValue)
XDOMGetOwnerDocument(nodeHandle, domHandle)
XDOMGetUserData(nodeHandle, userData)
XDOMItem(nodeListHandle, index, dataHandle, dataType)
XDOMLength(nodeListHandle, length)
XDOMLocate(xmlHandle, xpathString, nsMap, nodeHandle)
XDOMLocateNode(nodeHandle, direction, childIndex, nodeType, newNodeHandle)
XDOMOpen(xmlDocument, docLocation, domHandle)
XDOMQuery(xmlHandle, xquery, xqueryLocation, itemListHandle)
XDOMRemove(xmlHandle, xpathString, nsMap, attrName, nodeHandle)
XDOMReplace(xmlHandle, xpathString, nsMap, nodeHandle, dupFlag)
XDOMSetNodeValue(nodeHandle, nodeValue)
XDOMSetUserData(nodeHandle, userData)
XDOMTransform(domHandle, styleSheet, ssLocation, outDomHandle)
XDOMValidate(xmlDocument, docLocation, schFile, schLocation)
XDOMWrite(domHandle, xmlDocument, docLocation)
XLATE([DICT] filename, record.ID, field#, control.code)
XMAPAppendRec(XMAPhandle, file_name, record)
XMAPClose(XMAP_handle)
XMAPCreate(u2xmapping_rules, mapping_flag, XMAPhandle)
XMAPOpen(xml_document, doc_flag, u2xmapping_rules, u2xmap_flag, XMAPhandle)
XMAPReadNext(XMAPhandle, file_name, record)
XMAPToXMLDoc(XMAPhandle, xmlfile, doc_flag)
XMLError(errmsg)
XMLExecute(cmd, options, xmlvar, xsdvar)
XMLTODB(xml_document, doc_flag, u2xmapping_rules, u2xmap_ flag, status)
XTD(string)
~~~
