# toHex-fromHex
These are the routines I've created to convert an ASCII string to or from hexadecimal.
They can be converted to work with Unicode easily.  Unlike other functions that
do this - these routines are as fast as I could make them.  The only IF statement
in the functions are to test if the incoming string really isn't a string (ie: it
is a number of some kind).  If so, it converts the incoming information into a string
and proceeds.  Unlike other functions, this one can not return an odd length string.
(Which means that the leading zero (0) is missing.

The toHex() function only uses one function call.  This is to the charCodeAt() function
to return which character we are trying to convert.  This could probably be removed and replaced
with the "s[i]" string as that is an alternative to calling the function.

The fromHex() function only uses three functions.  Two charCodeAt() calls and one fromCharCode().
As before, the two charCodeAt() functions could probably be replaced by the "s[i]" and "s[i+1]"
calls.  Unfortunately, I do not know of any way to replace the fromCharCode() function and it
is relatively fast anyway.

Since toHex() is doing just simple math and using a lookup string - this should be a lot
quicker than a program that uses a lot of IF statements.

fromHex() will be a bit slower because of the three function calls and two IF statements
but I believe it will be faster than some of the other functions I have seen.

You can include these into an object (to keep them from colliding with other functions of the same name)
by just doing this:

if( typeof &lt;OBJ>.toHex == "undefined" ){
&lt;OBJ>.toHex = function(s)
{
   ...
}
}

and

if( typeof &lt;OBJ>.fromHex == "undefined" ){
&lt;OBJ>.fromHex = function(s)
{
   ...
}
}

Have fun! :-)
