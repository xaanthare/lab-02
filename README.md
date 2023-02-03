# Lab 2
[Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo and clone it to your machine to get started!

## Team Members
- Isabel Fernandez
- Aline Garcia-Sanchez

## Lab Question Answers

Question 1: How did the reliability of UDP change when you added 50% loss to your local environment? Why did this occur? 

-When doing this, more packets were lost since UDP does not check that the server recived it. Since we added 50% loss to the environment, it showed that the packets were lost and nothing showed up on the server side.

Question 2: How did the reliability of TCP change? Why did this occur? 

-TCP still recieved all the packets but the impact of the 50% loss environment caused a time delay where it was really slow.

Question 3: How did the speed of the TCP response change? Why might this happen? 

-TCP was much slower at reiceving the packets. This is due to the fact that it verifies that it was recieved. It is slower, yet it makes sure everything is transferred rather than losing some packets.

1. What is argc and *argv[]?
     argc = ./server
     argv[] = port number

2. What is a UNIX file descriptor and file descriptor table?
 A file descriptor is a number used by the computer to identify files… They are unique. A file descriptor table is a table (array) used to map the file descriptors to the open files. 


3. What is a struct? What's the structure of sockaddr_in?
     A struct is a list of data members that are grouped together

4. What are the input parameters and return value of socket()
     the return value is an integer 
    the parameters are also integers
5. What are the input parameters of bind() and listen()?
     int bind(int sockfd, const struct sockaddr *addr, socklen_t addrlen);
     int listen(int sockfd, int backlog);
6.  Why use while(1)? Based on the code below, what problems might occur if there are multiple simultaneous connections to handle?
        We want it to keep running and checking if something has been received. If there are multiple connections to handle, there might be packet losses in the receiving end. This is the case of polling but interrupts would be more efficient
7. Research how the command fork() works. How can it be applied here to better handle multiple connections?
	Forking duplicates the calling process of the files… the child process will run in a separate memory than its parent. To better handle multiple connections, forking helps by allowing for the running of the same code multiple times since it is run separately from its parent. Since this code runs in an infinite while loop, having multiple connections would not work. Forking it would allow several clients to communicate with the server at the same time. 

