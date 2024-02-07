import requests
import random
import string
import time
from pprint import pprint
import base64


emails = [
]

password = 'xxxx'
host = 'https://xxxx'

try:

    for email in emails:
        encoded_email = base64.b64encode(email.encode()).decode()

        headers = {
            'Content-Type': 'application/x-www-form-urlencoded; charset=UTF-8',
            'User-Agent': 'Dalvik/2.1.0 (Linux; U; Android 11; Redmi K20 Pro Premium Edition Build/RKQ1.200826.002)',
            'Connection': 'Keep-Alive',
        }

        data = {
            'password': 'xxx',
            'email': encoded_email,
        }

        response = requests.post(host+'/xxx', headers=headers, data=data)
        response_data = response.json()

        if response_data["status"]:
            apikey = response_data["apikey"]
            print("API Key:", apikey)
        else:
            print("Failed to fetch API Key. Error:", response_data["msg"])

        time.sleep(65)
        recheck_data = {
            'apikey': apikey,
            'email': email,
        }

        recheck_response = requests.post(host+'/xxxx', headers=headers, data=recheck_data)
        recheck_response_data = response.json()

        if recheck_response_data["status"]:
            balance = recheck_response_data["balance"]
            last_active = recheck_response_data["last_active"]
            last_update = recheck_response_data["last_update"]
            referral_last_update = recheck_response_data["referral_last_update"]
            print("Balance:", balance)
        else:
            print("Failed to fetch balance. Error:", recheck_response_data["msg"])


        time.sleep(145)
        mining_data = {
            'balance': balance,
            'apikey': apikey,
            'last_update': '2024-02-07 11:18:37',
            'last_active': '2024-02-07 11:18:37',
            'referral_last_update': '2024-02-07 11:18:37',
            'email': email,
        }
        pprint(mining_data)
        mining_response = requests.post(host+'/xxxxx', headers=headers, data=mining_data)
        print(mining_response.text)

        if mining_response["code"] != 0:
            error_response = requests.get('https://sctapi.ftqq.com/xxxxx.send?title=签到出错')
            print(error_response.text)


except Exception as e:
    raise e
