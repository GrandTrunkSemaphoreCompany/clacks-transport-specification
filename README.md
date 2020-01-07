# Clacks Transport Specification

- 8 shutters
- 7 bit ascii
- inverted per _code_
- permanant indicator flags below the shutters
- message made up of _overhead_ and an optional _body_
- _overhead_ made up of codes each with optional args
- any unrecogised control codes must be ignored

<message> = <overhead> [ <sot> <body> <eot> ]
<overhead> = <control code> [ <control args> ] [ <overhead> ]
<control code> = ( G | N | U | A | E | C | O | L | X )
<control args> = ( any printable 7 bit ascii code except <control code>, can be surounded by whitespace )
<body> = ( any printable 7 bit ascii code except <eot> )

example messages:
- A frank O 181 <SOT> Hello, this is bob.<EOT>
- GNU Terry Pratchet
- O 181 C image/gif E base64 L 16 X 33ef2cde <SOT>ABeGgg287sj3823=<EOT>
  
  
