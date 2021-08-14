
website : anycaptcha.com

* solver recaptchaV2, recaptchaV3, hcaptcha, funcaptcha, imageToTexxt , .... Super fast and cheapest.

* Install library :

      cd anycaptcha-python
      pip install -e .

* read demo.py to know how to use the library


Example : solver recaptcha v2:

    url = "https://www.google.com/recaptcha/api2/demo"
    site_key = "6Lc9qjcUAAAAADTnJq5kJMjN9aD1lxpRLMnCS2TR"
    api_key = "YOURAPIKEY"
    client = AnycaptchaClient(api_key)
    is_invisible=True
    task = RecaptchaV2TaskProxyless(website_url=url, website_key=site_key,is_invisible=is_invisible)
    job = client.createTask(task)
    job.join(maximum_time=120)
    result=job.get_solution_response()
    if result.find("ERROR") != -1:
        print("fail ",result)
    else:
        print("success ",result)

