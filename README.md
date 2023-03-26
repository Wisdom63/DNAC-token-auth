# DNAC-token-auth
DNAC token request
import requests
import json
from getpass import getpass
from requests.auth import HTTPBasicAuth

requests.packages.urllib3.disable_warnings()

USER = input('Enter your username please: ')
PASS = getpass('Enter your password for please: ')

post_url = 'https://sandboxdnac.cisco.com/dna/system/api/v1/auth/token'

payload={}
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  }

resp = requests.post(post_url, auth=HTTPBasicAuth(USER, PASS), headers=headers, verify=False)

response_json = resp.json()

print ("\Raw response from POSt token request:\n",resp.text)
