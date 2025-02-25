# Rocket UniVerse (U2) mvbasic cheat sheet

- Simple syntax listing. See Rocket's online documentation for more info
- Scraped from the UV Basic documentation v11.4.1 Aug 2023 [UNV-1141-BASR-1]
- Keywords are case insensitive eg `ACTIVATEKEY` ≈ `ActivateKey` ≈ `activatekey`
- Comments may appear at end of line _`;* comment`_

## TOC

- [Operators](#operators)
  - [Arithmetic Operators](#arithmetic-operators)
  - [Compound Assignment Operators](#compound-assignment-operators)
  - [Logical Operators](#logical-operators)
  - [Pattern Matching Operators](#pattern-matching-operators)
  - [Relational Operators](#relational-operators)
  - [String Operators](#string-operators)
- [Statements and Functions](#statements-and-functions)
- [@Macros](#macros)
- [SYSTEM() functions](#special-system-functions)
- [BASIC subroutines](#basic-subroutines)

## Operators

### Arithmetic Operators

<!-- ~~~ mvbasic -->
> expression **+** expression  
> expression **-** expression  
> expression **\*** expression  
> expression **/** expression  
> expression **^** expression  _;* (**)_

### Compound Assignment Operators

> variable **=** expression  
> variable **+=** expression _;* var = var + exp_  
> variable **-=** expression _;* var = var - exp_  
> variable **:=** expression _;* var = var : exp_

### Logical Operators

> expression **AND** expression _;* (&)_  
> expression **OR** expression  _;* (!)_  
> **NOT**(expression)

### Pattern Matching Operators

> expression **MATCH** pattern  _;* MATCHES_

### Relational Operators

> expression **=** expression  _;* (EQ)_  
> expression **#** expression  _;* (NE,<>,><)_  
> expression **<** expression  _;* (LT)_  
> expression **>** expression  _;* (GT)_  
> expression **<=** expression _;* (LE,=<,#>)_  
> expression **>=** expression _;* (GE,=>,#<)_

### String Operators

> expression **:** expression  
> expression **[** [ start,] [-]length **]**  
> expression **[** delimiter, occurrence, fields **]** _;* FIELD(delimiter, occurrence, fields)_

#### Equivalent Dynamic Array Logical and Relational Functions

> ADDS(exp1, exp2)  
> ANDS(exp1, exp2)  
> CATS(exp1, exp2)  
> DIVS(exp1, exp2)  
> EQS(exp1, exp2)  
> GES(exp1, exp2)  
> GTS(exp1, exp2)  
> IFS(exp1, exp2, exp3)  
> LES(exp1, exp2)  
> LTS(exp1, exp2)  
> MULS(exp1, exp1)  
> NES(exp1, exp2)  
> NOTS(exp1)  
> ORS(exp1, exp2)  
> SUBS(exp1, exp2)

## Statements and Functions

~~~ mvbasic
! [comment.text]                    ;* "*", REM, $*
#INCLUDE [filename] program         ;* INCLUDE, $INCLUDE
#INCLUDE program FROM filename
$* [comment.text]                   ;* "*", "!", REM
$CHAIN [filename] program
$COPYRIGHT "copyright.notice"
$DEFINE identifier [replacement.text]
$EJECT
$IFDEF identifier [statements] [[$ELSE] [statements]] $ENDIF
$IFNDEF identifier [statements] [[$ELSE] [statements]] $ENDIF
$INCLUDE [filename] program         ;* INCLUDE, #INCLUDE
$INCLUDE program FROM filename
$INSERT primos.pathname
$MAP mapname
$OPTIONS [flavor] [options]         ;*(PICK,INFORMATION,REALITY,IN2,DEFAULT,PIOPEN)
$UNDEFINE identifier
* [comment.text]                    ;* "!", REM, "$*"
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
ADDS(dynamic.array1, dynamic.array2)
ALPHA(expression)
amInitialize(hSession, appName, policyName, reasonCode)
amReceiveMsg(hSession, receiverName, policyName, selMsgName, maxMsgLen,dataLen, data, rcvMsgName, reasonCode[,recMsgOption])
amReceiveRequest(hSession, receiverName, policyName, maxMsgLen,dataLen, data, rcvMsgName, senderName, reasonCode [,recReqOption])
amSendMsg(hSession, senderName, policyName, data, sndMsgName,reasonCode)
amSendRequest(hSession, senderName, policyName, responseName, data,sndMsgName, reasonCode)
amSendResponse(hSession, senderName, policyName, rcvMsgName, data,sndMsgName, reasonCode)
amTerminate(hSession, policyName, reasonCode)
analyzeCertificate(cert, format, result, p12pass)
ANDS(dynamic.array1, dynamic.array2)
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
CATS(dynamic.array1, dynamic.array2)
CENTURY.PIVOT(year | nn )
CHAIN command
CHANGE(expression, substring, replacement [,occurrence [,begin]] )
CHAR(expression)
CHARS(dynamic.array)
CHECKSUM(string)
CLEAR [COMMON]
CLEARCOMMON [/common.label/]
CLEARDATA
ClearDiagnostics()
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
DIVS(dynamic.array1, dynamic.array2)
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
EQS(dynamic.array1, dynamic.array2)
EQU symbol TO expression [,symbol TO expression …]
EQUATE symbol TO expression [,symbol TO expression …]
EQU symbol LIT[ERALLY] string [,symbol LIT string …]
EQUATE symbol LIT[ERALLY] string [,symbol LIT string …]
EREPLACE(expression, substring, replacement [,occurrence [,begin]] )
ERRMSG message.ID [,message.ID …]
EXCHANGE(string, xx, yy)
EXEC commands [CAPTURING variable] [PASSLIST [dynamic.array]] [RTNLIST [variable]] [{SETTING | RETURNING} variable]
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
GARBAGECOLLECT ;*? reserved word - not verb
GCI ;*? reserved word - not verb
GCDISTANCE(lat1,lon1,lat2,lon2)
generateKey(privKey, pubKey, format, keyLoc, algorithm, keyLength, passPhrase, paramFile)
generateKey(privKey, pubKey, format, keyLoc, algorithm, keyLength, passPhrase, paramFile)
GES(dynamic.array1, dynamic.array2)
GET read.var[, length] [SETTING read.count] FROM device [UNTIL eop.char.list ] [RETURNING last.char.read ] [WAITING seconds ] [THEN statements ] [ELSE statements]
GETX read.var[, length] [SETTING read.count] FROM device [UNTIL eop.char.list ] [RETURNING last.char.read ] [WAITING seconds ] [THEN statements ] [ELSE statements]
getCipherSuite(context,ciphers)
getIpv([networkexpr])
GET(ARG. [,arg#] ) variable [THEN statements] [ELSE statements]
GetDiagnostics()
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
GTS(dynamic.array1, dynamic.array2)
HEADING [ON print.channel] heading
HEADINGE [ON print.channel] heading
HEADINGN [ON print.channel] heading
HMAC(hmacAlg, hmacKey, hmacData, [outFormat])
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
INMAT([dim.array])
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
LES(dynamic.array1, dynamic.array2)
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
LTS(dynamic.array1, dynamic.array2)
MAT dim.array = expression
MAT dim.array1 = MAT dim.array2
MATBUILD dynamic.array FROM dim.array [,start [,end]] [USING delimiter]
MATCHFIELD(string, pattern, field)
MATPARSE dim.array FROM dynamic.array [,delimiter]
MATPARSE dim.array [,start [,end]] FROM dynamic.array [USING delimiter] [SETTING elements]
MATREAD dim.array FROM [file.variable,] record.ID [ON ERROR statements] {THEN statements [ELSE statements] | ELSE statements}
MATREADL dim.array FROM [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
MATREADU dim.array FROM [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] {THEN statements [ELSE statements] | ELSE statements}
MATWRITE dim.array ON | TO [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
MATWRITEU dim.array ON | TO [file.variable,] record.ID [ON ERROR statements] [LOCKED statements] [THEN statements] [ELSE statements]
MAXIMUM(dynamic.array)
MINIMUM(dynamic.array)
MOD(dividend, divisor)
MODS(dynamic.array1, dynamic.array2)
MQCLOSE(hConn, hObj, options)
MQCONN(qManager, hConn)
MQDISC(hConn)
MQGET(hConn, hObj, msgDesc, getMsgOpts, msgBufferLen, msg,  msgDataLen)
MQGETERROR(reasonCode, reasonMessage)
MQINQ(hConn, hObj, selectors, attrs)
MQOPEN(hConn, objDesc, options, hObj)
MQPUT(hConn, hObj, msgDesc, putMsgOpts, msg)
MQPUT1(hConn, objDesc, msgDesc, putMsgOpts, msg)
MULS(dynamic.array1, dynamic.array2)
NAP [milliseconds]
NEG(number)
NEGS(dynamic.array)
NES(dynamic.array1, dynamic.array2)
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
ORS(dynamic.array1, dynamic.array2)
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
PyCallMethod(pyobject, methodName [,arg1, arg2, ...])
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
READBLK variable FROM file.variable, blocksize { THEN statements [ELSE statements] | ELSE statements }
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
SetDiagnostics(text)
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
SPLICE(dynamic.array1, expression, dynamic.array2)
SQLAllocConnect(bci.env, connect.env)
SQLAllocEnv(bci.env)
SQLAllocStmt(connect.env, statement.env)
SQLBindCol(statement.env, col#, data.type, column)
SQLBindParameter( statement.env, mrk#, data.type, sql.type, prec, scale, param [ , param.type ] )
SQLCancel(statement.env)
SQLColAttributes(statement.env, col#, col.attribute, text.var, num.var)
SQLColumns(statement.env, schema, owner, tablename, columnname)
SQLConnect(connect.env, data.source, logon1, logon2)
SQLDescribeCol(statement.env, col#, col.name, sql.type, prec, scale, null)
SQLDisconnect(connect.env)
SQLError(bci.env, connect.env, statement.env, sqlstate, dbms.code, error)
SQLExecDirect(statement.env, statement)
SQLExecute(statement.env)
SQLFetch(statement.env)
SQLFreeConnect(connect.env)
SQLFreeEnv(bci.env)
SQLFreeStmt(statement.env, option)
SQLGETDATA(stmt.env, loc, type, retvar, len)
SQLGetInfo(connect.env, info.type, info.value)
SQLGetTypeInfo(statement.env, sql.type)
SQLNumParams(statement.env, parameters)
SQLNumResultCols(statement.env, cols)
SQLParamOptions(statement.env, option, value)
SQLPrepare(statement.env, statement)
SQLRowCount(statement.env, rows)
SQLSetConnectOption(connect.env, option, value)
SQLSpecialColumns(statement.env, col.type, schema, owner,  tablename, IDscope, null)
SQLStatistics(statement.env, schema, owner, tablename, index.type, accuracy)
SQLTables(statement.env, schema, owner, tablename, type)
SQLTransact(bci.env, connect.env, type)
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
SUB [name] [([MAT] variable [, [MAT] variable …] )]
SUBROUTINE [name] [([MAT] variable [, [MAT] variable …] )]
SUBS(dynamic.array1, dynamic.array2)
SUBSTRINGS(dynamic.array, start, length)
SUM(dynamic.array)
SUMMATION(dynamic.array)
SWAP variable1, variable2
SWAP MAT dim.array, MAT dim.array
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
XDOMInsert(xmlHandle, xpathString, nsMap, nodeHandle, dupFlag)
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
XMLSetOptions("options")
XMLGetOptions(outOptions[, delimiterString])
XMLGetOptionValue(optionName, outOptionValue)
XMLTODB(xml_document, doc_flag, u2xmapping_rules, u2xmap_ flag, status)
XTD(string)
~~~

## @Macros

Sometimes called "@Variables". ( _RO_ = Read-Only).

| Macro | RO | Description |
|-|-|-|
| @ABORT.CODE | * | A numeric value indicating the type of condition that caused the ON.ABORT paragraph to execute. The values are:<br>1 – An ABORT statement was executed.<br>2 – An abort was requested after pressing the Break key followed by option A.<br>3 – An internal or fatal error occurred.<br>4 – An AUTO.LOGOUT event occurred.
| @ACCOUNT | * | User login name. Same as @LOGNAME. Nonstacked. |
| @AM | * | Field mark: CHAR(254). Same as @FM. |
| @ANS | | Last I-type answer, value indeterminate. |
| @AUTHORIZATION | * | Current effective user name. |
| @COMMAND | * | Last command executed or entered at the UniVerse prompt. |
| @COMMAND.STACK | * | Dynamic array containing the last 99 commands executed. |
| @CONV | | For future use. |
| @CRTHIGH | * | Number of lines on the terminal. |
| @CRTWIDE | * | Number of columns on the terminal. |
| @DATA.PENDING | * | Dynamic array containing input generated by the DATA statement. Values in the dynamic array are separated by field marks. |
| @DATE | | Internal date when the program was invoked. |
| @DAY | | Day of month from @DATE. |
| @DICT | | For future use. |
| @FALSE | * | Compiler replaces the value with 0. |
| @FILE.NAME | | Current file name. When used in a virtual field index, @FILENAME reflects the current file name being used in a RetrieVe or UniVerse SQL statement. Same as @FILENAME. Note:  The @FILENAME variable is also populated during a BUILD.INDEX command using the CONCURRENT option so that I-type indexes using @FILENAME will be built correctly. |
| @FILENAME | | Same as @FILE.NAME. |
| @FM | * | Field mark: CHAR(254). Same as @AM. |
| @FORMAT | | For future use. |
| @HDBC | * | ODBC connection environment on the local UniVerse server. Nonstacked. |
| @HEADER | | For future use. |
| @HENV | * | ODBC environment on the local UniVerse server. Nonstacked. |
| @HSTMT | * | ODBC statement environment on the local UniVerse server. Nonstacked. |
| @ID | | Current record ID. |
| @IDX.FILEPATH | * | Can be used within an indexed subroutine. Contains the full path of the UniVerse file being updated that caused the indexed subroutine to fire. |
| @IDX.IOTYPE | * | Specifies the type of operation being performed. Can be integrated in the indexed subroutine to determine they type of database operation that caused the indexed subroutine to fire. The following values are associated with the @IDX.IOTYPE:<br>0 - The value returned when @IDX.IOTYPE is used outside the context of an indexed subroutine.<br>1 - The value returned when the SUBR is called because an INSERT operation is performed.<br>2 - The value returned when the SUBR is called because a DELETE operation is performed.<br>3 - The value returned when the SUBR is called because an UPDATE operation is used to evaluate the original value operation.<br>4 - The value returned when a SUBR i called because an UPDATE operation is used to evaluate the new value operation. |
| @IM | * | Item mark: CHAR(255). |
| @ISOLATION | * | Current transaction isolation level for the active transaction or the current default isolation level if no transaction exists. |
| @LEVEL | * | Nesting level of execution statements. Nonstacked. |
| @LOGNAME | * | User login name. Same as @ACCOUNT. |
| @LPTRHIGH | * | Number of lines on the device to which you are printing (that is, terminal or printer). |
| @LPTRWIDE | * | Number of columns on the device to which you are printing (that is, terminal or printer). |
| @MONTH | | Current month. |
| @MV | | Current value counter for columnar listing only. Used only in I- descriptors. Same as @NV. |
| @NB | | Current BREAK level number. 1 is the lowest-level break. |
| @NB | | has a value of 255 on the grand total line. Used only in I- descriptors. |
| @ND | | Number of detail lines since the last BREAK on a break line. Used only in I-descriptors. |
| @NI | | Current item counter (the number of items listed or selected). Used only in I-descriptors. Same as @RECCOUNT. |
| @NS | | Current subvalue counter for columnar listing only. Used only in I-descriptors. |
| @NULL | * | The null value. Nonstacked. |
| @NULL.STR | * | Internal representation of the null value, which is CHAR(128). Nonstacked. |
| @NV | | Current value counter for columnar listing only. Used only in I- descriptors. Same as @MV. |
| @OPTION | | Value of field 5 in the VOC for the calling verb. |
| @PARASENTENCE | * | Last sentence or paragraph that invoked the current process. |
| @PATH | * | Path name of the current account. |
| @PYEXCEPTIONMSG | * | A string that stores the detailed exception message. If no exception is thrown, its value is an empty string. |
| @PYEXCEPTIONTRACEBACK | * | A string that stores the traceback of the exception. If no exception is thrown, its value is an empty string. |
| @PYEXCEPTIONTYPE | * | A string that stores the exception type. If no exception is thrown, its value is an empty string. |
| @RECCOUNT | | Current item counter (the number of items listed or selected). Used only in I-descriptors. Same as @NI. |
| @RECORD | | Entire current record. |
| @RECUR0 | | Reserved. |
| @RECUR1 | | Reserved. |
| @RECUR2 | | Reserved. |
| @RECUR3 | | Reserved. |
| @RECUR4 | | Reserved. |
| @SCHEMA | * | Schema name of the current UniVerse account. Nonstacked. When users create a new schema, @SCHEMA is not set until the next time they log in to UniVerse. |
| @SELECTED | | Number of elements selected from the last select list. Nonstacked. |
| @SENTENCE | | Sentence that invoked the current BASIC program. Any EXECUTE statement updates @SENTENCE. |
| @SM | * | Subvalue mark: CHAR(252). Same as @SVM. |
| @SQL.CODE | * | For future use. |
| @SQL.DATE | * | Current system date. Use in trigger programs. Nonstacked. |
| @SQL.ERROR | * | For future use. |
| @SQL.STATE | * | For future use. |
| @SQL.TIME | * | Current system time. Use in trigger programs. Nonstacked. |
| @SQL.WARNING | * | For future use. |
| @SQLPROC.NAME | * | Name of the current SQL procedure. |
| @SQLPROC.TX.LEVEL | * | Transaction level at which the current SQL procedure began. |
| @STDFIL | | Default file variable. |
| @SVM | * | Subvalue mark: CHAR(252). Same as @SM. |
| @SYS.BELL | * | Bell character. Nonstacked. |
| @SYSTEM.RETURN.CODE | | Status codes returned by system processes. Same as @SYSTEM.SET. |
| @SYSTEM.SET | | Status codes returned by system processes. Same as @SYSTEM.RETURN.CODE. |
| @TERM.TYPE | * | Terminal type. Nonstacked. |
| @TIME | | Internal time when the program was invoked. |
| @TM | * | Text mark: CHAR(251). |
| @TRANSACTION | * | A numeric value. Any nonzero value indicates that a transaction is active; the value 0 indicates that no transaction exists. |
| @TRANSACTION.ID | * | Transaction number of the active transaction. An empty string indicates that no transaction exists. |
| @TRANSACTION.LEVEL | * | Transaction nesting level of the active transaction. A 0 indicates that no transaction exists. |
| @TRUE | * | Compiler replaces the value with 1. |
| @TTY | | Terminal device name. If the process is a phantom, @TTY returns the value ‘phantom’. If the process is a UniVerse API, it returns ‘uvcs’. Note: In PI/Open flavor, @TTY returns an empty string for PHANTOM processes. |
| @TZ | | Since datetime is stored as UTC, in order to consider the timezone of the current user when converting to and from the locale date and time, a new @-variable called @TZ has been introduced. @TZ is a per-process variable which defaults to an empty string. If @TZ is empty, the timezone in use will refer to the user’s TZ environment variable (if set) or to the system’s timezone setting if it is not set. The @TZ value can be set to any time zone supported by the underlying operating system. For Unix and Linux, it can be names supported by the tz database. When converting datetime from and to the local date and time, @TZ will be used as the local time zone. The exception is when during ICONV() and OCONV() for datetime, if a timezone is specified in the conversion code or the data to be converted, the @TZ’s value will be overridden.<br>_Note_:  This variable is supported on Linux and Solaris platforms only. |
| @U2PY | | A string that returns the number of the Python level at whichthe current BASIC program is running. Without Python, @U2PY has the value of 0. With Python, @U2PY has the value of a positive integer. Note:  SYSTEM(55) has been implemented to return the samevalue as @U2PY. |
| @USER0 | | User-defined. |
| @USER1 | | User-defined. |
| @USER2 | | User-defined. |
| @USER3 | | User-defined. |
| @USER4 | | User-defined. |
| @USERNO | * | User number. Nonstacked. Same as @USER.NO. |
| @USER.NO | * | Same as @USERNO. |
| @USER.RETURN.CODE | | Status codes created by the user. |
| @VM | * | Value mark: CHAR(253). |
| @WHO | * | Name of the current UniVerse account directory. Nonstacked. |
| @YEAR | | Current year (2 digits). |
| @YEAR4 | | Current year (4 digits). |

## Special SYSTEM() functions

\<\<TBC\>\>

(_int_ = integer, _bool_ = Boolean)

| Code | Description |
|-|-|
|0999 | ASSIGN `@TRUE` TO SYSTEM(999)" which disables "Q" at the "Press... " prompt |
|1002 | Indicates if file is in rotating file pool |
|1003 | Indicates if print job is in process |
|1005 | `@FALSE` if pagination is disabled, `@TRUE` if enabled. Can ASSIGN to system(1005). |
|1006 | Indicates if cursor is at left margin |
|1012 | Page header (set with HEADING) |
|1017 | ASSIGN `@TRUE` to SYSTEM(1017). In UniData the equivalent command for no conversion is "NOCONVERT [ON \| OFF]". |
|1030 | Parse `@SENTENCE` retaining quoted literals (returns `@AM` delimited string), i.e THIS IS "MY TEST" on command line will be returned as THIS`@AM`IS`@AM`MY TEST ( 3 instead of 4 arguments) |
|1050 | TRAP key array (set with KEYTRAP and documented in KEYEDIT) |
|1301 | Effective user name |
|1302 | LISTU data, one attribute per user (not confirmed) |
|3001 | ASSIGN TO SYSTEM(3001) through SYSTEM(3005) to fire counters for the Windows NT performance monitor. |
|4001 | `@FALSE` for normal command line prompt (">"). Set to `@TRUE` to change the command line prompt to the value of System(4002). |
|4002 | Dynamic Array<3>. The replacement command line prompt, e.g., ":" instead of ">". Can be multiple chars, e.g., "DEV>". `<1>` is the replacement string for the normal prompt; `<2>` for the select-list-active prompt; `<3>` the command continuation prompt. |
|9001 | returns name of current subroutine -- actually name of current object path in SYSTEM(9001)<1,2>. The dynamic array returned contains the whole stack of object paths. Aborts if called by UO.NET. |
|9010 | Returns database type UD, UV, UD.PE or UV.PE (UDT 7.1.5 or later) |

- **SYSTEM(1030)** returns _@AM_ delimited version of _@SENTENCE_ [per space, "except quotes"]
  - eg _>PROG\_ARG1\_"ARG\_2"\_ \_ARG4_ -> PROG`@AM`ARG1`@AM`ARG 2`@AM` `@AM`ARG4

- **SYSTEM(9001)** returns call stack. Name of current prog: SYSTEM(9001)<1,2>, parent prog: SYSTEM(9001)<2,2>, etc

- **ASSIGN _int_ TO SYSTEM(1)** sets print channel _int_ active. [default] _int_ = -1

  _Use the following in conjunction with SYSTEM(1), active printer channel_

  - ASSIGN _bool_ TO SYSTEM(1005) turn on/off pagination [true=on/false=off]
  - ASSIGN _int_ TO SYSTEM(1008) changes active printer channel width to _int_
  - ASSIGN _int_ TO SYSTEM(1009) changes active printer channel depth to _int_
  - ASSIGN _int_ TO SYSTEM(1010) changes active printer channel top margin to _int_
  - ASSIGN _int_ TO SYSTEM(1011) changes active printer channel bottom margin to _int_

  **Example**
  
  ~~~ mvbasic
  ASSIGN 5 TO SYSTEM(1)    ;* set to print channel 5
  PRINT "This goes to print channel 5 as if 'PRINT ON 5'"
  ASSIGN 64 TO SYSTEM(1009)
  PRINT "Change the (page) depth to 64 lines on PC 5"
  OPENPATH '/mygraphics' TO dirfv ELSE STOP
  ASSIGN @TRUE TO SYSTEM(1017)  ;* set 'raw' read mode
  READ logo.pcl FROM dirfv,'logo.pcl' ELSE STOP
  PRINT logo.pcl ;* read and print a raw graphic
  ASSIGN @FALSE TO SYSTEM(1017) ;* reset file read mode
  ASSIGN -1 TO SYSTEM(1)   ;* set PC back to user's terminal
  PRINT "Back on user's terminal"
  ~~~

- **ASSIGN _int_ TO SYSTEM(225)** changes active USERNO to _int_

- **ASSIGN _bool_ TO SYSTEM(999)"** which enables(@false)/disables(@true) "Q" at the "Press... " prompt

- **ASSIGN _bool_ TO SYSTEM(1017)** changes how Type19 records are read/written.
  - ASSIGN _@TRUE_ TO SYSTEM(1017) will result in no conversion, so reads and writes will retain NL or @AM chars
  - ASSIGN _@FALSE_ TO SYSTEM(1017) [default] will result in all NL (newline) chars converted to _@AM_ chars on reads, and _@AM_ chars to NL chars on writes

- **ASSIGN _int_ TO SYSTEM(2101)** LIST.READU display

- **ASSIGN _bool_ TO SYSTEM(4001)** enable/disable custom uvshell prompt
  - ASSIGN _@TRUE_ TO SYSTEM(4001) enable custom uvshell prompt defined in SYSTEM(4002)
  - ASSIGN _@FALSE_ TO SYSTEM(4001) disable custom uvshell prompt. Resumes default uvshell prompt (>)
- **ASSIGN _dynamic.array_ TO SYSTEM(4002)** define custom uvshell prompt. Dynamic.array contains:

   > <1> custom uvshell prompt string - eg `DEV#>`
   > <2> custom select-list-active prompt string - eg `DEV>>`
   > <3> custom command-continuation prompt string - eg `DEV?>`

## BASIC subroutines

| Subroutine | Equivalent Function |
|-|-|
| !ASYNC(key, line, data, count, carrier) _;* !AMLC_ | |
| !EDIT.INPUT(keys, wcol, wrow, wwidth, buffer, startpos, bwidth, ftable, code) | |
| !ERRNO(variable) | |
| !FCMP(result, number1, number2) | |
| !GET.KEY(string, code) | |
| !GET.PARTNUM(file, record.ID, partnum, status) | |
| !GET.PATHNAME(pathname, directoryname, filename, status) | |
| !GET.USER.COUNTS(uv.users, max.uv.users, os.users) | |
| !GET.USERS(uv.users,max.users,sys.users,user.info,code) | |
| !GETPU(key, print.channel, set.value, return.code) | |
| !INLINE.PROMPTS(result, string) | |
| !INTS(result, dynamic.array) | |
| !MAKE.PATHNAME(path1, path2, result, status) | |
| !MATCHES(result, dynamic. array, match.pattern) | |
| !MESSAGE(key, username, usernum, message, status) | |
| !PACK.FNKEYS(trap.list, ftable) | |
| !REPORT.ERROR(command, subroutine, code) | |
| !SET.PTR(print.channel, width, length, top.margin, bottom.margin, mode, options) | |
| !SETPU(key, print.channel, new.value, return.code) | |
| !TIMDAT(variable) | |
| !USER.TYPE(type, admin) | |
| !VOC.PATHNAME(data/dict, voc.entry, result, status) | |
| !ADDS | ADDS |
| !ANDS | ANDS |
| !CATS | CATS |
| !CHARS | CHARS |
| !CLEAR.PROMPTS | CLEARPROMPTS |
| !COUNTS | COUNTS |
| !DISLEN | LENDP |
| !DIVS | DIVS |
| !EQS | EQS |
| !FADD | FADD |
| !FDIV | FDIV |
| !FIELDS | FIELDS |
| !FMTS | FMTS |
| !FMUL | FMUL |
| !FOLD | FOLD |
| !FSUB | FSUB |
| !GES | GES |
| !GTS | GTS |
| !ICONVS | ICONVS |
| !IFS | IFS |
| !INDEXS | INDEXS |
| !LENS | LENS |
| !LES | LES |
| !LTS | LTS |
| !MAXIMUM | MAXIMUM |
| !MINIMUM | MINIMUM |
| !MODS | MODS |
| !MULS | MULS |
| !NES | NES |
| !NOTS | NOTS |
| !NUMS | NUMS |
| !OCONVS | OCONVS |
| !ORS | ORS |
| !SEQS | SEQS |
| !SPACES | SPACES |
| !SPLICE | SPLICE |
| !STRS | STRS |
| !SUBS | SUBS |
| !SUBSTRINGS | SUBSTRINGS |
| !SUMMATION | SUMMATION |

---
The end
