                                               Name:Pradeep V
                                               Reg No:212223240119
# EX-5:Multiple server with infinite capacity - (M/M/c):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](https://user-images.githubusercontent.com/103921593/203238035-1c8109bc-cbf2-4c77-baea-c5b682a752ef.png)

## Procedure :

![203238265-176740b0-eae2-4772-90be-5449869ac9b0](https://github.com/velupradeep/Muttiple-capacity-with-infinite-capacity/assets/150329341/e07915c7-90c6-4897-b0fd-e1bbb5bee03b)





## Experiment:
![313417011-28b8d6b5-4c74-48b8-844a-d662f7a7a9f2](https://github.com/velupradeep/Muttiple-capacity-with-infinite-capacity/assets/150329341/eaae1e59-65d2-4cbc-879e-48b3a4aad3da)
![313417018-ddc9de93-a9f8-43a0-8c66-9b99f586cb7a](https://github.com/velupradeep/Muttiple-capacity-with-infinite-capacity/assets/150329341/97cc0eeb-f023-4417-afef-24d850569285)



## Program
```
import math
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time=float(input("Enter the mean  inter service time of Lathe Machine (in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))
c=int(input("Number of service centre :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("--------------------------------------------------------------")
print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
rho=lam/(c*mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(rho))
    print("Probability that the system is empty : %0.2f "%(1-rho))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
```


## Output :
![313417040-63426fc3-af90-4de7-90b9-b65d7e6ce82a](https://github.com/velupradeep/Muttiple-capacity-with-infinite-capacity/assets/150329341/fbfeccfa-3c8c-47e6-8206-2da37560f188)

## Result : 
Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.

