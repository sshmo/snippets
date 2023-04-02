# filling a javascript protected feild
  
  from selenium.webdriver.common.action_chains import ActionChains
  
  feild = driver.find_element_by_...
  string = 'some string'
  ActionChains(driver).move_to_element(feild).click().key_down(Keys.CONTROL).send_keys('a').key_up(Keys.CONTROL).send_keys(string).perform()
