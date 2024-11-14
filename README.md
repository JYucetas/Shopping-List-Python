# Shopping-List-Python

import sys,time

sl = []

def mainScreen():
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("     SHOPPING LIST    ")
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("\nYour list contains",len(sl),"items.\n")
	print("Please choose from the following options:\n")
	print("1- add to the list")
	print("2- delete from the list")
	print("3- view the list")
	print("4- quit the program")
	choice = input("\nchoice: ")
	if len(choice) > 0:
		if choice[0] == "1":
			addScreen()
		elif choice[0] == "2":
			deleteScreen()
		elif choice[0] == "3":
			viewScreen()
		elif choice[0] == "4":
			sys.exit()
		else:
			mainScreen()
	else:
		mainScreen()
	

def addScreen():
	global sl 
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("     ADD SCREEN    ")
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("\n\n")
	print("Please enter the name of the item that you want to add.")
	print("Press ENTER to return to the main menu.\n")
	item = input("\nItem: ")
	if len(item) > 0:
		sl.append(item)
		print("Item added")
		time.sleep(1)
		addScreen()
	else:
		mainScreen()
	


def viewScreen():
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("     VIEW SCREEN    ")
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("\n")
	for item in sl:
		print(item)
	
	print("\n")
	print("Press enter to return to the main menu")
	input()
	mainScreen()
	

	
def deleteScreen():
	global sl
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	print("     DELETE SCREEN    ")
	print("%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%")
	count = 0
	for item in sl:
		print(count, " - ", item)
		count = count + 1
	print("What number to delete?")
	choice = input("number: ")
	if len(choice) > 0:
		try:
			del sl[int(choice)]
			print("Item deleted...")
			time.sleep(0)
		except:
			print("Invalid number")
			time.sleep(1)
		deleteScreen()
	
	else:
		mainScreen()
		
	
mainScreen()
