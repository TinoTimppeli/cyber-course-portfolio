Decimal	Binary
10	00001010 (example — done for you)
210	11010010
168	10101000
16	00010000
255	11111111
128	10000000
192	11000000
248	11111000
0	00000000


Binary	Decimal
11000000	192
11111111	255
10101000	168
00010000	16
11111000	248
11010010	210


1.3 - Full-address conversion

10.210.168.16 - 00001010.11010010.10101000.00010000

192.168.0.1 - 11000000.10101000.00000000.00000001

172.16.5.100 - 10101100.00010000.00000101.01100100

dotted decimal

11000000.10101000.00000001.00000001 → 192.168.1.1

00001010.00001010.00000000.01001011 → 10.10.0.75


Address	Class	Default mask (dotted)	Default mask (CIDR)
10.0.0.5	A	255.0.0.0	/8
192.168.1.1	C	255.255.255.0	/24
172.16.4.20	B	255.255.0.0	/16
8.8.8.8	A	255.0.0.0	/8
200.100.50.25	C	255.255.255.0	/24



Dotted-decimal	CIDR	Binary (32 bits)
255.255.255.0	/24	11111111.11111111.11111111.00000000
255.255.0.0	/16	11111111.11111111.00000000.00000000
255.0.0.0	/8	11111111.00000000.00000000.00000000
255.255.255.192	/26	11111111.11111111.11111111.11000000
255.255.248.0	/21	11111111.11111111.11111000.00000000
255.255.255.128	/25	11111111.11111111.11111111.10000000



2.3 - Networks and hosts per class


Class	Default CIDR	Number of possible networks	Number of hosts per network
A	/8	128 nets	16 million hosts
B	/16	16,384 nets	65,534 hosts
C	/24	2,097,152 nets	254 hosts




2.1 - What class is it?


Address	Class	Default mask (dotted)	Default mask (CIDR)
10.0.0.5	 	 	 
192.168.1.1	 	 	 
172.16.4.20	 	 	 
8.8.8.8	 	 	 
200.100.50.25	 	 	 

Address	Class	Default mask (dotted)	Default mask (CIDR)
10.0.0.5	A	255.0.0.0	/8
192.168.1.1	C	255.255.255.0	/24
172.16.4.20	B	255.255.0.0	/16
8.8.8.8	A	255.0.0.0	/8
200.100.50.25	C	255.255.255.0	/24





2.2 - Mask ↔ CIDR ↔ binary

Dotted-decimal	CIDR	Binary (32 bits, dots between octets)
255.255.255.0	/24	11111111.11111111.11111111.00000000
255.255.0.0	 	 
 	/8	 
255.255.255.192	 	 
 	/21	 
255.255.255.128



Dotted-decimal	CIDR	Binary (32 bits)
255.255.255.0	/24	11111111.11111111.11111111.00000000
255.255.0.0	/16	11111111.11111111.00000000.00000000
255.0.0.0	/8	11111111.00000000.00000000.00000000
255.255.255.192	/26	11111111.11111111.11111111.11000000
255.255.248.0	/21	11111111.11111111.11111000.00000000
255.255.255.128	/25	11111111.11111111.11111111.10000000



You said:

2.3 - Networks and hosts per class
Complete the table (from your lesson notes):

Class	Default CIDR	Number of possible networks	Number of hosts per network
A	/8	128 nets	16 million hosts
B	/16	 	 
C	/24

ChatGPT said:
Class	Default CIDR	Number of possible networks	Number of hosts per network
A	/8	128 nets	16 million hosts
B	/16	16,384 nets	65,534 hosts
C	/24	2,097,152 nets	254 hosts




Task 3 

3.1 — 172.16.0.0/16
subnet mask:       255.255.0.0
network address:   172.16.0.0
default gateway:   172.16.0.1
host range start:  172.16.0.2
host range end:    172.16.255.254
broadcast:         172.16.255.255

3.2
subnet mask:       255.255.255.192
network address:   10.10.0.0
default gateway:   10.10.0.1
host range start:  10.10.0.2
host range end:    10.10.0.62
broadcast:         10.10.0.63
	
3.3
subnet mask:       255.255.255.240
network address:   192.168.5.0
default gateway:   192.168.5.1
host range start:  192.168.5.2
host range end:    192.168.5.14
broadcast:         192.168.5.15

3.4
subnet mask:       255.255.255.252
network address:   10.0.0.0
default gateway:   10.0.0.1
host range start:  10.0.0.2
host range end:    10.0.0.2
broadcast:         10.0.0.3


3.5
subnet mask:       255.255.255.128
network address:   192.168.100.128
default gateway:   192.168.100.129
host range start:  192.168.100.130
host range end:    192.168.100.254e
broadcast:         192.168.100.255


Task 4 - Which subnet does this host belong to?

4.1 — 10.10.0.75/26
Network address:  10.10.0.64
Broadcast:        10.10.0.127
yes its is a valid host

4.2 — 192.168.1.200/26
Network address:  192.168.1.192
Broadcast:        192.168.1.255
yes a valid host


4.3 — 172.16.5.130/25
Network address:  172.16.5.128
Broadcast:        172.16.5.255
yes a valid host

4.4 — 10.0.0.0/30
Network address:  10.0.0.0
Broadcast:        10.0.0.3
not a valid host


Task 5 - Slicing up a /24
You've been given the network 192.168.10.0/24 and need to divide it into smaller subnets for four departments.

5.1 - Four equal /26 subnets
Divide 192.168.10.0/24 into four equal /26 subnets. For each of the four resulting subnets, write out:

Network address
Default gateway
Host range (start–end)
Broadcast address
(You should end up with subnets starting at .0, .64, .128, and .192 — matching the block sizes you calculated in class: /24 = 256, /25 = 128, /26 = 64.)


