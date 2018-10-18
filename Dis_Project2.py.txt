#Disassembler for Machine Code

input_file = open("Machine_Code_Project2.txt","r") 	#Reads MachineCode	
output_file = open("Assembly_Code_Project2.txt","w") 	#Writes ISA

for line in input_file:
	if(line == "\n"):
		continue		#Empty lines are ingonred
	line = line.replace ("\n","") 	#Removes the 'endline' character
	line = line.replace (" ","")	#Removes the spaces anywhere in the line

if(line[1:4] =='000'):			
	op ="Init"
	register = format(int(line[4:6], 2))
	immediate = format(int(line[6:8], 2))
	print(op + " $R" + register +" " + immediate + "\n")
	output_file.write(op + " $R" + register +" " + immediate + "\n")

elif(line[1:4] =='001'):
	op ="j"
	immediate = format(int(line[4:8], 2))
	output_file.write(op + "j" + immediate + "\n")

elif(line[1:4] =='010'):
	op ="Beq"
	immediate = format(int(line[4:8], 2))
	output_file.write(op + " Beq" + immediate + "\n")

elif(line[1:4] =='011'):
	op ="Add"
	rt = format(int(line[4:6], 2))
	rs = format(int(line[6:8], 2))
	output_file.write(op + " $R" + rt + " $R" + rs + "\n")

elif(line[1:4] =='100'):
	op ="Sub"
	rt = format(int(line[4:6], 2))
	rs = format(int(line[6:8], 2))
	output_file.write(op + " $R" + rt + " $R" + rs + "\n")

elif(line[1:4] =='101'):
	op ="SLT"
	rt = format(int(line[4:6], 2))
	rs = format(int(line[6:8], 2))
	output_file.write(op + " $R" + rt + " $R" + rs + "\n")

elif(line[1:6] =='11000'):
	op ="Shl"
	rt = format(int(line[6:8], 2))
	output_file.write(op + "$R" + rt + "\n")

elif(line[1:6] =='11011'):
	op ="Shr"
	rt = format(int(line([6:8], 2))	
	output_file.write(op + "$R" + rt + "\n")

elif(line[1:6] =='110'):
	op ="XOR"
	rs = format(int(line[6:8], 2))
	output_file.write(op + " $R1" + " $R" + rs + "\n")

elif(line[1:6] =='11010'):
	op ="Load"
	rt = format(int(line[6:8], 2))
	output_file.write(op + " $R" + rt + "\n")

elif(line[1:6] =='11100'):
	rt= format(int(line[6:8], 2))
	output_file.write(op + " $R" + rt + "\n")

elif(line[1:8] =='1111111'):
	op="End"
	output_file.write(op + "\n")
input_file.close()
output_file.close()

	

		

	
