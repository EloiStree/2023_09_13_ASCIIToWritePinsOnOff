# 2023_09_13_ASCIIToWritePinsOnOff
The idea is to have a microcontroller that can turn on and off pin from a ASCII index in aim to minimized the bluetooth slow interaction.


I experimented a small problem with HC06... It is very very very slow and if you speed it up you lose data.
So with 9600 the only way to make it "fast" is to turn byte in actions instead of using text commands.
A char is 

```
↑ ↓ → ←
32	 
33	!  D01↓
34	"  D01↑
35	#  D02↓
36	$  D02↑
37	%  D03↓
38	&  D03↑
39	'  D04↓
40	(  D04↑
41	)  D05↓
42	*  D05↑
43	+  D06↓
44	,  D06↑
45	-  D07↓
46	.  D07↑
47	/  D08↓
48	0  D08↑
49	1  D09↓
50	2  D09↑
51	3  D10↓
52	4  D10↑
53	5  D11↓
54	6  D11↑
55	7  D12↓
56	8  D12↑
57	9  D13↓
58	:  D13↑
59	;  D14↓
60	<  D14↑
61	=  D15↓
62	>  D15↑
63	?  D16↓
64	@  D16↑
65	A  D17↓
66	B  D17↑
67	C  D18↓
68	D  D18↑
69	E  D19↓
70	F  D19↑
71	G  D21↓
72	H  D21↑
73	I  D22↓
74	J  D22↑
75	K  D23↓
76	L  D23↑
77	M  D24↓
78	N  D24↑
79	O  D25↓
80	P  D25↑
81	Q  D26↓
82	R  D26↑
83	S  D27↓
84	T  D27↑
85	U  D28↓
86	V  D28↑
87	W  D29↓
88	X  D29↑
89	Y  D30↓
90	Z  D30↑
91	[  D31↓
92	\  D31↑
93	]  GPIO 01↓
94	^  GPIO 01↑
95	_  GPIO 02↓
96	`  GPIO 02↑
97	a  GPIO 03↓
98	b  GPIO 03↑
99	c  GPIO 04↓
100	d  GPIO 04↑
101	e  GPIO 05↓
102	f  GPIO 05↑
103	g  GPIO 06↓
104	h  GPIO 06↑
105	i  GPIO 07↓
106	j  GPIO 07↑
107	k  GPIO 08↓
108	l  GPIO 08↑
109	m  GPIO 09↓
110	n  GPIO 09↑
111	o  GPIO 10↓
112	p  GPIO 10↑
113	q  GPIO 11↓
114	r  GPIO 11↑
115	s  GPIO 12↓
116	t  GPIO 12↑
117	u  GPIO 13↓
118	v  GPIO 13↑
119	w  GPIO 14↓
120	x  GPIO 14↑
121	y  GPIO 15↓
122	z  GPIO 15↑
123	{  GPIO 16↓
124	|  GPIO 16↑
125	}  GPIO 17↓
126	~  GPIO 17↑
127	D  GPIO 18↓
128	Ç  GPIO 18↑
129	ü  GPIO 19↓ 
130	é  GPIO 19↑
131	â  GPIO 21↓	 
132	ä  GPIO 21↑ 
133	à  GPIO 22↓
134	å  GPIO 22↑
135	ç  GPIO 23↓
136	ê  GPIO 23↑	 
137	ë  GPIO 24↓
138	è  GPIO 24↑
139	ï  GPIO 25↓
140	î  GPIO 25↑	
141	ì  GPIO 26↓
142	Ä  GPIO 26↑
143	Å  GPIO 27↓
144	É  GPIO 27↑
145	æ  GPIO 28↓
146	Æ  GPIO 28↑
147	ô  GPIO 29↓	
148	ö  GPIO 29↑
149	ò  GPIO 30↓
150	û  GPIO 30↑
151	ù  GPIO 31↓
152	ÿ  GPIO 31↑
153	Ö 
154	Ü 
155	ø 
156	£ 
157	Ø 
158	× 
159	ƒ 
160	á 
161	í 
162	ó 
163	ú 
164	ñ 
165	Ñ 
166	ª 
167	º 
168	¿ 
169	® 
170	¬ 
171	½ 
172	¼ 
173	¡ 
174	« 
175	» 
176	░ 
177	▒ 
178	▓ 
179	│ 
180	┤ 
181	Á 
182	Â 
183	À 
184	© 
185	╣ 
186	║ 
187	╗ 
188	╝ 
189	¢ 
190	¥ 
191	┐ 
192	└ 
193	┴ 
194	┬ 
195	├ 
196	─ 
197	┼ 
198	ã 
199	Ã 
200	╚ 
201	╔ 
202	╩ 
203	╦ 
204	╠ 
205	═ 
206	╬ 
207	¤ 
208	ð 
209	Ð 
210	Ê 
211	Ë 
212	È 
213	ı 
214	Í 
215	Î 
216	Ï 
217	┘ 
218	┌ 
219	█ 
220	▄ 
221	¦ 
222	Ì 
223	▀ 
224	Ó 
225	ß
226	Ô		
227	Ò
228	õ
229	Õ
230	µ
231	þ
232	Þ
233	Ú	
234	Û		
235	Ù
236	ý
237	Ý
238	¯
239	´
240	¬
241	±
242	‗
243	¾
244	¶ Request Bluetooth Log state  0101010#47689
245	§ Request Bluetooth Log full Text description
246	÷ Test One by one digital
247	¸ Test One by one analog
248	° Test One by one All
249	¨ Turn on All analog
250	• Turn on All buttons
251	¹ Turn on all currents B0 A0
252	³ Cut All analog
253	² Cut All buttons
254	■ Cut all currents B0 A0 
		
```
