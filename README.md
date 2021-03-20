# Check-in_out-Automation

from intornaUserInfo import username, password
from selenium import webdriver
import time


class Intorna:
    def __init__(self, username, password):
        self.browser = webdriver.Chrome()
        self.username = username
        self.password = password
        
        
    def signIn(self):
        self.browser.get("http://app.intorna.com/app/auth/login")
        time.sleep(2)
        
        self.browser.find_element_by_xpath("//*[@id='input-email']").send_keys(self.username)
        self.browser.find_element_by_xpath("//*[@id='input-password']").send_keys(self.password)
        time.sleep(1)
        
        self.browser.find_element_by_xpath("//*[@id='form-login']/button").click()
        time.sleep(2)
    
        
    def doCheckInCheckOut(self):
        self.browser.get("http://app.intorna.com/app/student/intern_attendance")
        time.sleep(2)
        
        self.browser.find_element_by_xpath("//*[@id='intern_attendance-page-content-wrapper']/div/div/div[2]/div/div[1]/div/div/div/a").click() 
        time.sleep(2)
        
        self.browser.find_element_by_xpath("/html/body/div[7]/div[7]/div/button").click()
        time.sleep(2)
        
        self.browser.find_element_by_xpath("//*[@id='intern_attendance-page-content-wrapper']/div/div/div[2]/div/div[1]/div/div/div/a").click() 
        time.sleep(2)
        
        self.browser.find_element_by_xpath("/html/body/div[7]/div[7]/div/button").click()
        time.sleep(8)
        
        self.browser.find_element_by_xpath("//*[@id='bs-example-navbar-collapse-1']/ul[2]/li/a").click()
        time.sleep(2)
        
        self.browser.find_element_by_xpath("//*[@id='bs-example-navbar-collapse-1']/ul[2]/li/ul/li[4]/a").click()
        time.sleep(2)
           
        
intorna = Intorna(username, password)
intorna.signIn()
intorna.doCheckInCheckOut()
