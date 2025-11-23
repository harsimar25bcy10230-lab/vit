import os
import time

if "data" not in os.listdir():
    os.mkdir("data")

total = 0
attended = 0
file = "data/att.txt"


try:
    f = open(file)
    line = f.readline()
    f.close()
    if line:
        x = line.split(",")
        total = int(x[0])
        attended = int(x[1])
except:
    pass

while 1:
    print("\n\n")
    print(" ATTENDANCE TRACKER")
    

    if total == 0:
        per = 0
    else:
        per = attended * 100 / total

    print("Total classes :", total)
    print("I attended    :", attended)
    print("Percentage    :", per, "%") # FIX: Display 'per' variable

    if per >= 75:
        print(">>> OKAY SAFE")
    else:
        print(">>> IT IS SAFE")

    print("1 = update")
    print("2 = bunk check")
    print("3 = exit")

    ans = input("input ")

    if ans == "1":
        try:
            newt = input("total classes (" + str(total) + "): ")
            newa = input("attended (" + str(attended) + "): ")
            if newt != "":
                total = int(newt)
            if newa != "":
                if int(newa) > total:
                    print("bhai jhooth mat bol")
                else:
                    attended = int(newa)
        except:
            print("type number only")

    elif ans == "2":
        print("\ncalculating...")
        

        if per >= 75:
        
            bunkpossible = 0
            tempheld = total + 1
            tempatt = attended
            while tempatt * 100 / tempheld >= 75:
                bunkpossible += 1
                tempheld += 1
            print("you can miss", bunkpossible, "classes")
        else:
            # same stupid way
            need = 0
            tempheld = total
            tempatt = attended
            while tempatt * 100 / tempheld < 75:
                need += 1
                tempheld += 1
                tempatt += 1
            print("must attend next", need, "classes")

        input("\npress enter...")

    elif ans == "3":
        f = open(file,"w")
        f.write(str(total) + "," + str(attended)) 
        f.close()
        print("saved")
        break
