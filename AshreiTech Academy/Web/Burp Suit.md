
## Modules
- Snipper attack only use when we have only one position set for brute force in intruder.
- We only use one list for one payload parameter in snipper attack.

- Buttering ram attack use when we have one or more than one position set for brute force in intruder.
- We only use one list for one payload in buttering ram attack.

- Pitchfork attack use when we have multiple position set for brute force in intruder.
- The number of list depends on the parameters we selected.
- Corresponding entries.
	- Example 3 selected params and 3 lists
	- Param 1, list 1 first entry and so on, Param 2, list 2 first entry and so on, Param 3, list 3 first entry and so on
	- Param 2, list 1 second entry and so on, Param 2, list 2 second entry and so on, Param 3, list 3 second entry and so on

- Cluster bomb attach use when we have multiple position set for brute force in intruder.
- The number of list depends on the parameters we selected.
- All combinations:
	- Example 3 selected params and 3 lists
	- Param 1, list 1 first entry and so on, list 2 all one by one, list 3 all one by one
	- Param 2, list 1 all one by one, list 2 first entry and so on, list 3 all one by one
	- Param 3, list 1 first entry, list 2 all one by one, list 3 all one by one

Content length (validation message) and response receive shows which password matched on brute force by intruder.

Grep match will highlight the response specific flag. Example: "Invalid username / password"

Decoder is used to decode any encoded format using this burp suit.

Collaborator is used for blind testing. Example: blind XSS.

Comparer is used for comparing 2 strings to check for match.

Extensions for burp suit.