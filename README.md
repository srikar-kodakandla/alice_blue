# Fully automated Alice Blue Algo Trading with Python on NSE and MCX for Nifty / Crude / Banknifty futures and options (option buying only) , absolutely FREE !
This algo trading bot is my first attempt to try, learn and implement my python programming skills. Please use this only for reference and at your own risk.  
This repository contains python code to perform algo trading on India, NSE through AliceBlue broker. 
You need to have a valid AliceBlue client ID, password, 2FA authentication password set and API enabled (ask aliceblue support) to get this working.
Initially, I had developed this for windows then later moved to linux (ubuntu) platform on AWS.

There are 2 programs. You can run either one of them on a single linux (It should run on windows as well, I have not yet tested though) machine.  
1. For Options trading (Requires 10-15k capital) - ab_options.py which uses ab_options.ini as configuration/parameter file.
   <br>Usage : > python ab_options.py 
   This program is for option buying only.
   
2. For Futures trading (Requires 2.5-4 lakhs capital) - ab.py which uses ab.ini as configuration/parameter file.
   <br>Usage : > python ab_options.py
   This program is focused on Nifty and Crude futures with a simple Supertrend with RSI strategy.
   
These programs basically uses 3min (low) , 6min (medium) time frame supertrend and RSI indicators (adjusted through parameters) to generate signals. For any other strategy you need to modify the main program. My wish list includes parameterisation of this strategy peice as well. 

There is also a background program (ab_bg.py) which when triggered runs at the background and helps us to control our algo bot from anywhere using telegram. 
We can send commands through telegram chats to do various activities in realtime like start/stop trading, set MTM levels, manage SL, get detailed logs etc. 
basically all the realtime config parameters can be managed/modified through telegram chats.    

The main program ab.py/ab_options.py which needs to be scheduled at 8:59:30 AM / 9:14:00 AM daily through linux crontab. 
Crude(MCX) opens at 9:00 AM and Nifty at 9:15 AM.
You can setup AWS instance to start at 8:45 AM and stop at 11:45 PM (After MCX Close) through AWS Lambda. 
I typically set both of the programs on seperate AWS instances and configure two seperate IDs. 
You can read through the comments in the ab.py/ab_options.py for detailed understanding. 
# There is an ab.ini/ab_options.ini file which is the key configuration file through which you can control all the parameters of this program, even at realtime using Telegram chats. 

As a onetime setup, please create log and data folder in the same path where the program files are copied.

Although this is still work in progress, kindly suggest your feedback. It will help me improve.

Feel free to use/distribute this code freely so that new algo developers can get started easily.  

For folks who are interested in learning Algo Programming for Indian Stock exchanges can join this informative, valuable and highly active Telegram Group
https://t.me/AlgoTradeAnalysis
(Please note this is not my Telegram Group)
