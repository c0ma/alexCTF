import socket
```
import sys

sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_address = ("195.154.53.62", 7331)
sock.connect(server_address)

try:
    while 1:
        data = sock.recv(1024)
        print  data
        try:
                problem = data.split(":")[1]
                problem = problem.split(" ")
                n1 = int(problem[0])
                n2 = int(problem[2]) 
                if problem[1] == "+":
                        print str(n1 + n2)
                        sock.sendall(str(n1 + n2) + "\n")
                if problem[1] == "-":
                        print n1 - n2
                        sock.sendall(str(n1 - n2) + "\n")
                if problem[1] == "*":
                        print n1 * n2
                        sock.sendall(str(n1 * n2) + "\n")
                if problem[1] == "%":
                        print n1 % n2
                        sock.sendall(str(n1 % n2) + "\n")
                if problem[1] == "/":
                        print n1 / n2
                        sock.sendall(str(n1 / n2) + "\n")
        except:
                print "no data recived "
                break

finally:
    sock.close()

# Well no human got time to solve 500 ridiculous math challenges
# Congrats MR bot!
# Tell your human operator flag is: ALEXCTF{1_4M_l33t_b0t}
```
