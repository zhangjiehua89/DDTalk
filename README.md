# DDTalk
DDtalk 报业绩
import requests
import json

def getDingMes():

baseUrl = "https://oapi.dingtalk.com/robot/send?access_token=40ca5202d7d5af4f0c4154f66e12cb66ef9938671e6dc07c0b8a9326e96051df"
 7 
# please set charset= utf-8
HEADERS = {
    "Content-Type": "application/json ;charset=utf-8 "
     }
 
 # 这里的message是你想要推送的文字消息
     message = "今天的业绩是多少？大家"
     stringBody ={
         "msgtype": "text",
         "text": {"content": message},
         "at": {
             "atMobiles": ["1"],
                "isAtAll": True   #@所有人 时为true，上面的atMobiles就失效了
         }
  }
  MessageBody = json.dumps(stringBody)
     result = requests.post(url=baseUrl, data=MessageBody, headers=HEADERS)
     print(result.text)
 
 if __name__ == '__main__':
    getDingMes()
