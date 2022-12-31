# gen

	gen - generate wordlists from a character set

SYNOPSIS
	gen <min-len> <max-len> [<charset string>] [options]

DESCRIPTION
	gen generate a wordlist based on how specified your options. The output from gen can be sent to the screen, file, of to another program.

	min-len and max-len
		The minimum length and maximun length string you want gen to start and end at.

	charset string
		You may specify character sets for gen to use on the command line or if you leave it blank gen will use the default character sets.


OPTIONS
	-t
		This option ingore <charset string>. This is where you specify a patten, eg: @@god@@@ which @'s, ,'s, %'s, and ^'s are set of characters. Unlike crunch "gen 2 3 -t %men" is the same as "gen 2 3 0123456789men".
		@ will insert lower case characters
		, will insert upper cae characters
		% will insert numbers
		^ will insert symbols


	-s
		Make options "-t" to operate same as option in crunch. eg: @@god@@@ where the only the @'s, ,'s, %'s, and ^'s will change.

  -S "n;{<charset string>}"
    n is the position where u place your characters. same as -s but gives nth added characters.
    this option is not done yet.

	-p word1 word2 ...
		Tell gen to treat words as characters.

EXAMPLES
  1) gen 2 3 abcde
    gen will generate from aa to eee.
  
  2) gen 2 3 -t %
    gen will generate from 00 to 999.
  
  3) gen 2 3 -t %@
    gen will generate from 00 to aaa.
  
  4) gen -t %mpho -s
    gen will generate from 0mpho to 9mpho.
  
  5) gen -t dani@l% -s
   gen will generate from danial0 to danizl9.
  
  6) gen -t daniel -S "2;{ei}"
    gen will generate from daniel to diniel.
    the outcome will go as: daniel
                            deniel
                            diniel
    only the position nth will change.
  
  7) gen -p mpho pamphang daniel
    gen will generate from mphomphompho to danieldanieldaniel.
