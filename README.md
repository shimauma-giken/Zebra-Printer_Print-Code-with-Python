# Zebra-Printer_Print-Code-with-Python

Pythonを用いて印刷をするソースコード

Network Printing Python Example  
Article ID:000013719  •  April 12, 2018  
https://supportcommunity.zebra.com/s/article/Network-Printing-Python-Example?language=en_US  


	import socket   
	import traceback
	
	printer = "192.168.4.59" 
	port = 9100   
	
	mysocket = socket.socket(socket.AF_INET,socket.SOCK_STREAM)         
	
	try:           
	    # connecting to host
		mysocket.connect((printer, port))
	    
	    # Send ZPL (send by byte) 
		mysocket.send(b"^XA^A0N,50,50^FO50,50^FDSocket Test^FS^XZ") 
	 
	    # Close Connection
		mysocket.close () 
	 
	except Exception:
	    traceback.print_exc()
	
