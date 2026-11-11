Exercise 03: Network Connectivity Testing

Objective

Test local network connectivity, external IP connectivity and DNS resolution using Kali Linux.

Commands Executed

1. Test local gateway

ping -c 4 192.168.100.1

Result: 4 packets transmitted, 4 received, 0% packet loss.

2. Test external connectivity

ping -c 4 8.8.8.8

Result: 4 packets transmitted, 4 received, 0% packet loss.

3. Test DNS resolution

getent hosts google.com

Result: Successfully returned an IPv6 address for google.com.

Findings

1. The Kali machine successfully communicated with its default gateway.
2. External IP connectivity was confirmed using Google’s public DNS IP address.
3. DNS resolution successfully returned an IPv6 address.
4. No packet loss was observed in either of the two ping tests.
5. External response times varied during the test.

Learning Outcomes

* Understood the purpose of the ping command.
* Learned how to test local network connectivity.
* Verified external IP connectivity.
* Practised DNS resolution.
* Interpreted packet loss and response-time statistics.

Conclusion

The connectivity tests confirmed that the Kali Linux machine had working local and external network connectivity during the exercise.

DNS resolution was also successful.

Environment: Kali Linux
Module: Networking Fundamentals
Exercise: Network Connectivity Testing
