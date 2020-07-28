# AI Meets Location

Ever wondered on how we can add AI when it comes to location based services? In this code we upload pass an image to a Python Flask Application and get recommendation based on the food picture you have passed.

#### Sign up for IBM Cloud at https://ibm.biz/HERETechnologies
#### Get your Here Maps API Key at https://developer.here.com

## Architecture 

![Arch](/images/AI_Location_Sol_Arch.png)

1. User passes an image in the python code
1. As we are using the visual recognition service there is a out of the box food model which we are going to use and it detects the name of the food which we have passed
1. The name of the food is then passed to the Here Maps Discover API which then suggests places around a particular location which we have configured within the python application.

### Local Deployment

To implement this code to a location of your choice 

1. Clone this repository 
```bash
git clone https://github.com/vidhanbhonsle/Visual-Recognition-with-IBM-HERE-and-Python
```
2. Add your IBM Cloud Visual Recogntion API Key and Here Maps API Key in ```test.py```

```python
authenticator = IAMAuthenticator('IBM_API_KEY')

visual_recognition = VisualRecognitionV3(
    version='2018-03-19',
    authenticator=authenticator)

visual_recognition.set_service_url('IBM_SERVICE_URL') 
```

3. Enter the templates directory and add the HERE maps API key obtained from developer.here.com and add it to the ```JS_API_KEY``` variable

```javascript
	 var platform = new H.service.Platform({
            apikey: "JS_API_KEY" //HERE MAPS API KEY   
        });
```

4. And scroll to the variables where the ```latitude``` and ```longitude``` are set and replace it with the latitude and longitude of your desired locaiton.
```python
latitude = 12.959111
longitude = 77.732022
```