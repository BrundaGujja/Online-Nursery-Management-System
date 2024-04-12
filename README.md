# Online-Nursery-Management-System
Python script manages gardening store: admins add/remove products, view earnings; users order, cancel, invoice. 
import random
def total_goods():
	sum=0
	quant=0
	for i in vegitables:
		sum+=i[3]*i[2]
		quant+=i[2]
	s=sum
	q=quant
	print("*VEGITABLES*")
	print("Quantity--%d\nIncome--%d"%(quant,sum))
	for i in fruits:
		sum+=i[3]*i[2]
		quant+=i[2]
	print("*FRUITS*")
	print("Quantity--%d\nIncome--%d"%(quant-q,sum-s))
	s=sum
	q=quant
	for i in flowers:
		sum+=i[3]*i[2]
		quant+=i[2]
	print("*FLOWERS*")
	print("Quantity--%d\nIncome--%d"%(quant-q,sum-s))	
	s=sum
	q=quant
	for i in fertilizers:
			sum+=i[3]*i[2]
			quant+=i[2]
	print("*FERTILIZERS*")
	print("Quantity--%d\nIncome--%d"%(quant-q,sum-s))
	s=sum
	q=quant
	for i in tools:
			sum+=i[3]*i[2]
			quant+=i[2]
	print("*GARDEN TOOLS*")
	print("Quantity--%d\nIncome--%d"%(quant-q,sum-s))
def remove_products():
	global ids
	global jaa
	global m12
	print("SELECT YOUR TYPE OF PRODUCT ")
	display_menu()
	print("----------*--*-")
	while(1):
		id_delete=input("ENTER ID NUMBER TO  PRODUCT:")
		if(id_delete.isdigit()):
			id_delete=int(id_delete)
			if(id_delete>0):
				break
			else:
				print("Enter correct ID..")
		else:
			print("Enter digits only")
	mmm=0
	if(ids==1):
			try:
				m1=-100
				for i in range(len(vegitables)):
					for j in range(len(vegitables[0])):
							if(vegitables[i][0]==id_delete):
								m1=i
								break
				if(jaa==0):
					del vegitables[m1]
				else:
					m12=vegitables[m1]
					vegitables[m1][2]-=1
			except:
				mmm=1
	if(ids==2):
				try:
					m1=-100
					for i in range(len(fruits)):
							for j in range(len(fruits[0])):
								if(fruits[i][0]==id_delete):
									m1=i
									break
					if(jaa==0):
						del fruits[m1]
					else:
						m12=fruits[m1]
						fruits[m1][2]-=1
				except:
					mmm=1
	if(ids==3):
				try:
					m1=-100
					for i in range(len(flowers)):
							for j in range(len(flowers[0])):
								if(flowers[i][0]==id_delete):
									m1=i
									break
					if(jaa==0):
						del flowers[m1]
					else:
						m12=flowers[m1]
						flowers[m1][2]-=1
				except:
					mmm=1
					
	if(ids==4):
				try:
					m1=-100
					for i in range(len(fertilizers)):
							for j in range(len(fertilizers[0])):
								if(fertilizers[i][0]==id_delete):
									m1=i
									break
					if(jaa==0):
						del fertilizers[m1]
					else:
						m12=fertilizers[m1]
						fertilizers[m1][2]-=1
				except:
					mmm=1
	if(ids==5):
				try:
					m1=-100
					for i in range(len(tools)):
							for j in range(len(tools[0])):
								if(tools[i][0]==id_delete):
									m1=i
									break
					if(jaa==0):
						del tools[m1]
					else:
						m12=tools[m1]
						tools[m1][2]-=1
				except:
					mmm=1
	if(mmm==1):
				if(jaa==0):
					print("PRODUCT NOT REMOVED BECAUSE ..")
				else:
					print("PRODUCT NOT PLACED BECAUSE..")
				print("THAT IS INVALID ID..")
	else:
				if(jaa==0):
					print("PRODUCT SUCCESSFULLY REMOVED..")
				else:
					print("PRODUCT SECCESSFULLY PLACED..")
					print("That is...%s"%(m12[1]))
				
			
	
def add_products():
	global ids
	print("SELECT YOUR TYPE OF PRODUCT ")
	display_menu()
	print("ENTER NEW PRODUCT DETAILS..")
	pro_name=input("Enter Product name:")
	pro_name=pro_name.upper()
	while(1):
		quantity=input("Enter product Quantity:")
		if(quantity.isdigit()):
			quantity=int(quantity)
			if(quantity>0):
				break
			else:
				print("Enter valid quantity..")
		else:
			print("Enter digits only..")
	while(1):
		money=input("Enter product Price:")
		if(money.isdigit()):
			money=int(money)
			if(money>0):
				break
			else:
				print("Enter valid Amount..")
		else:
			print("Enter digits only..")
	if(ids==1):
		nn=len(vegitables)
		vegitables.append([nn*nn,pro_name,quantity,money])
	if(ids==2):
		nn=len(fruits)
		fruits.append([nn*nn,pro_name,quantity,money])
	if(ids==3):
		nn=len(flowers)
		flowers.append([nn*nn,pro_name,quantity,money])
	if(ids==4):
		nn=len(fertilizers)
		fertilizers.append([nn*nn,pro_name,quantity,money])
	if(ids==5):
		nn=len(tools)
		tools.append([nn*nn,pro_name,quantity,money])
	print("SUCCESSFULLY PRODUCT IS ADDED")
	
	
	
def tool():
	global ids
	ids=5
	print("%s   \t%s               \t%s  \t%s"%(item[0],item[1],item[2],item[3]))
	for i in tools:
			print("%d    \t%s   \t\t%d  \t\t%d"%(i[0],i[1],i[2],i[3]))
	
def fertilizer():
	global ids
	ids=4
	print("%s   \t%s               \t%s  \t%s"%(item[0],item[1],item[2],item[3]))
	for i in fertilizers:
			print("%d    \t%s   \t\t\t%d  \t\t%d"%(i[0],i[1],i[2],i[3]))
def seed():
	global ids
	print("IN SEEDS WHAT YOU WANT...\n")
	print("  1)*VEGITABLES*")
	print("  2)*FRUITS*")
	print("  3)*FLOWERS*")
	while(1):
		seed_opt=input("Enter your option:")
		if(seed_opt.isdigit()):
			seed_opt=int(seed_opt)
			if(seed_opt>0 and seed_opt<4):
				break
			else:
				print("Enter correct option..")
		else:
			print("Enter digits only")
	print("%s   \t%s               \t%s  \t%s"%(item[0],item[1],item[2],item[3]))
	if(seed_opt==1):
		ids=1
		for i in vegitables:
			print("%d    \t%s          \t%d  \t\t%d"%(i[0],i[1],i[2],i[3]))
	elif(seed_opt==2):
		ids=2
		for i in fruits:
			print("%d    \t%s     \t\t%d  \t\t%d"%(i[0],i[1],i[2],i[3]))
	else:
		ids=3
		for i in flowers:
			print("%d    \t%s     \t\t%d  \t\t%d"%(i[0],i[1],i[2],i[3]))
def display_menu():
	print("  1)*SEEDS & SAPLINGS*")
	print("  2)*FERTILIZERS*")
	print("  3)*GARDEN TOOLS*\n")
	while(1):
		menu_opt=input("Enter your option:")
		if(menu_opt.isdigit()):
			menu_opt=int(menu_opt)
			if(menu_opt>0 and menu_opt<4):
				break
			else:
				print("Enter correct option..")
		else:
			print("Enter digits only..")
	if(menu_opt==1):
		seed()
	elif(menu_opt==2):
		fertilizer()
	elif(menu_opt==3):
		tool()
def invoice():
	global bill_items
	global item
	print("YOUR ORDERED ITEMS ARE..")
	print("---------")
	print("%s \t%s          \t%s \t%s"%("ID","NAME","QUA_","PRICE"))
	total=0
	for mm in bill_items:
		print("%d \t%s          \t%d \t%d"%(mm[0],mm[1],mm[2]-mm[2]+1,mm[3]))
		total=total+mm[3]
	print("------*--*")
	print("****TOTAL BILL=%d"%(total))
	
		
def cancel_order():
	global m12
	global order_id
	global ids
	global bill_items
	while(1):
		orderid=input("Enter your product order ID:")
		if(orderid.isdigit()):
			orderid=int(orderid)
			if(orderid>0):
				break
			else:
				print("Enter valid order ID..")
		else:
			print("Enter digits only..")
	for i in order_id.keys():
					if(orderid in order_id[i]):
						kmk=i
						km=""
						km1=""
						for k in i[1:]:
							if(k==']'):
								break
							km=km+k
						ind=i[1:].index("[")
						for nh in i[ind+2:]:
										if(nh=="]"):
											break
										km1=km1+nh
					
								
						i=[]
						i.append(km)
						i.append(int(km1))
						for kk in range(len(bill_items)):
							if(bill_items[kk][0]==i[1]):
								bill_items.pop(kk)
						print("Your ordered item is:",i[0])
						print("Successfully order is Cancelled..")
						order_id[kmk].remove(orderid)
						if(True):
							for j in vegitables:
								if(i[1]==j[0] and i[0]==j[1]):
									j[2]+=1
									break
						elif(True):
							for j in fruits:
								if(i[1]==j[0] and i[0]==j[1]):
									j[2]+=1
									break
						elif(True):
							for j in flowers:
								if(i[1]==j[0] and i[0]==j[1]):
									j[2]+=1
									break
						elif(True):
									for j in fertilizers:
										if(i[1]==j[0] and i[0]==j[1]):
											j[2]+=1
											break
						if(True):
									for j in fertilizers:
										if(i[1]==j[0] and i[0]==j[1]):
											j[2]+=1
											break
						if(True):
									for j in tools:
										if(i[1]==j[0] and i[0]==j[1]):
											j[2]+=1
											break
									
						break
	else:
		print("This is invalid OrderID or expaired OrderID...")
		
def place_order():
	global m12
	global bill_items
	global order_id
	global ids
	print("Selecet your Product..")
	global jaa
	jaa=1
	remove_products()
	if("1432" not in m12):
		orderid=random.randint(1000,9999)
		print("Your order ID is:",orderid)
		u=[]
		bill_items.append(m12)
		k="["+m12[1]+"]"+"["+str(m12[0])+"]"
		try:
			u=order_id[k]
		except:
			pass
		u.append(orderid)
		order_id[k]=u
		
		
	
def user_login():
	print("   1)**DISPLAY MENU**/")
	print("   2)**PLACE ORDER**/")
	print("   3)**CANCEL ORDER**/")
	print("   4)**INVOICE**/")
	print("   5)**LOGOUT**/")
	while(1):
		user_opt=input("Enter your option:")
		if(user_opt.isdigit()):
			user_opt=int(user_opt)
			if(user_opt>0 and user_opt<6):
				break
			else:
				print("Enter valid option...")
		else:
			print("Enter digits only...")
	if(user_opt==1):
		display_menu()
	elif(user_opt==2):
		place_order()
	elif(user_opt==3):
		cancel_order()
	elif(user_opt==4):
		pass
		invoice()
	if(user_opt!=5):
		print("----------------------*")
		user_login()	
	if(user_opt==5):
		print("You Are Logout is Succesfull\n\n")
		print("Enter '1'  for Login session\nOther wise enter any option")
		session_opt=input("Enter Your Option:")
		if(session_opt=='1'):
			print("\n\n")
			first_interface()
		else:
			print("\n\nYou successfully Quited\n**THANK YOU**")
			
def admin_login():
	print("   1)**DISPLAY MENU**/")
	print("   2)**ADD PRODUCTS**/")
	print("   3)**REMOVE PRODUCTS**/")
	print("   4)**TOTAL GOODS AVAILABLE & INCOME**/")
	print("   5)**LOGOUT**/")
	while(1):
		admin_opt=input("Enter your option:")
		if(admin_opt.isdigit()):
			admin_opt=int(admin_opt)
			if(admin_opt>0 and admin_opt<6):
				break
			else:
				print("Enter valid option...")
		else:
			print("Enter digits only...")
	if(admin_opt==1):
		display_menu()
	elif(admin_opt==2):
		add_products()
	elif(admin_opt==3):
		remove_products()
	elif(admin_opt==4):
		total_goods()
	if(admin_opt!=5):
		print("----------------------*")
		admin_login()	
	if(admin_opt==5):
		print("You Are Logout is Succesfull\n\n")
		print("Enter '1'  for Login session\nOther wise enter any option")
		session_opt=input("Enter Your Option:")
		if(session_opt=='1'):
			print("\n\n")
			first_interface()
		else:
			print("\n\nYou successfully Quited\n**THANK YOU**")
def first_interface():
	print("For Admin..section Enter 1 to Login")
	print("For User..section Enter 2 to Login")
	while(1):
		login_opt=input("Enter your option:")
		if(login_opt.isdigit()):
			login_opt=int(login_opt)
			if(login_opt==1 or login_opt==2):
				break
			else:
				print("Enter valid option...")
		else:
			print("Enter digits only..")
	i=3
	while(i>0):
		print("You have %d chances left"%(i))
		password=input("Enter Login password:")
		if(login_opt==1):
			if(password=="bunny"):
				print("/*Success*/")
				admin_login()
				break
		else:
			if(password=="harika"):
				print("/*Success*/")
				user_login()
				break
		print("Wrong password .......")
		i=i-1
	else:
		print("Your session is expired...")
item=["ID","NAME","ALB-QT","PRICE"]
vegitables=[]
fruits=[]
flowers=[]
fertilizers=[]
tools=[]
vegitables.append([1,"BRINJAL",100,57])
vegitables.append([2,"TOMATO",100,74])
vegitables.append([3,"CHILLI",100,27])
vegitables.append([4,"CABBAGE",100,42])
fruits.append([5,"GUAVA",100,10])
fruits.append([6,"MANGO",100,8])
fruits.append([7,"PAPAYA",100,20])
fruits.append([8,"BANANA",100,5])
flowers.append([9,"ROSE",100,5])
flowers.append([10,"JASMINE",100,7])
flowers.append([11,"LILLY",100,4])
flowers.append([12,"HIBISCUS",100,3])
fertilizers.append([13,"UREA",100,350])
fertilizers.append([14,"VERMICOMPOST",100,160])
fertilizers.append([15,"DAP",100,555])
fertilizers.append([16,"ROSE_BOOSTER",100,135])
tools.append([17,"POTS..",100,55])
tools.append([18,"WATERING_CAN",100,280])
tools.append([19,"SPADE",100,120])
tools.append([20,"GLOVES",100,50])
ids=0
jaa=0
bill_items=[]
order_id={}
m12=["1432"]
first_interface()
