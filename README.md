# Smart Home Application using AWS IoT Core and MQTT over WebSocket as Communication Protocol

> This work contains an Emulator and Client UI App that controls the emulator

## Abstract
This project discloses the development of a solution for realizing a smart home in the post COVID-19
era using the Internet of Things domain knowledge. COVID-19 outbreak has been catastrophic and
impacted everyone’s lives due to its rapid transmission from one body to another. This project aims to
reduce virus transmission by eliminating the need to touch any common-point surface in a home, such
as switches, doorknobs, and remotes. We provide a generic solution by coupling things with the internet
to control them remotely. The project aims to showcase a working solution to controlling devices like
smart bulbs, smart fans, smart ACs, and smart door locks in our self-developed emulator over WWW
securely using two different protocols, viz., HTTP and MQTT-over-WSS. Additionally, the MQTT is realized using AWS IoT JavaScript SDK based on AWS IoT Core service and HTTP is deployed on AWS EC2 using encryption and hashing from scratch. The developed project can be applied to any smart home setting like a hotel or public place using AWS IoT, Lambda, or similar infrastructure as a broker.

## Problem Statement
The world has observed the unprecedented COVID-19 outbreak, and it impacted the lives of millions. On the other hand, ICT or Industrial 4.0 has fully immersed into reality during this time. The transmission of COVID spread rapidly due to people being in proximity and sharing surfaces of everyday objects like doorknobs, switches, and various appliances' remote. Therefore, can technology to help reduce transmission and increase more contact-free and contact-less operations of daily life? 

The answer is YES using Internet of Things, but the question still remains how? Hence, we have used two communication protocols and compared which of them provides optimal payload delivery, latency and security guarantee. 

## Process for running the application

**STEP 1**: Run the Client App in one tab/window:

> Note: Please wait for 10-20 seconds as it connects to AWS IoT after Authentication is done from AWS Cognito Identity Pool

>Provide these test credentials while choosing between communication protocol:  
**Username**: muneeb  
**Password**: majid

https://mohdmajidakhtar.github.io/ELL893/client/

**STEP 2**: Run the Emulator App in another tab/window:
> We have designed our own simulation environment (Emulator App) as an HTML web page consisting of four kinds of smart devices: bulb, fan, AC, and door lock.

https://mohdmajidakhtar.github.io/ELL893/emulator/

**STEP 3**: Interact from MQTT client app and see changes in MQTT emulator 

## Work Flow Diagram

![MQTT AWT IoT Work Flow](https://github.com/mohdmajidakhtar/ELL893/blob/main/images/mqtt_aws_iot_workflow.png)

## MQTT Devices Payload structure

1. Smart Bulb
```json
{
	"device": "smart_bulb1",
	"params": {
		"power": true,
		"color": "#ffffff"
	}
}
```

2. Smart Lock
```json
{
	"device": "smart_lock1",
	"params": {
		"door_status": "locked"
	}
}
```

3. Smart Fan
```json
{
	"device": "smart_fan1",
	"params": {
		"power": true
	}
}
```

4. Smart AC
```json
{
	"device": "smart_ac1",
	"params": {
		"power": true,
		"h_direction": "rotate(0deg)",
		"temperature": 20
	}
}
```

## Logs and Reports
We have provided logs for different kinds of information with different color codes representing error logs, connection logs, command logs and response logs.  
![Logs](https://github.com/mohdmajidakhtar/ELL893/blob/main/images/logs.png)


#### Also See our HTTP implementation
> HTTP has been implemented by my partner Muneeb Ahmed
https://github.com/muneebpandith/ELL893


## Smart Home Architecture Diagram
![Smart Home Architecture Diagram](https://github.com/mohdmajidakhtar/ELL893/blob/main/images/smart_home.png)


## Conclusion
We observed MQTT over WSS to be more efficient as it provides low latency and better guarantee of delivery. The comparison is shown in figure below. 
![Latency Comparison between HTTP and MQTT-over-WSS](https://github.com/mohdmajidakhtar/ELL893/blob/main/images/mqtt_vs_http.png)  
We envision our solution is beneficial towards the society in reducing the transmission of novel COVID-19. Along with it, the developed project can be applied to any smart home setting like a hotel or public place where social distancing is required to reduce the transmission of virus by touching surfaces.


## Reference
1. IoT and non-IoT connections worldwide 2010-2025, Statista Report, 2021. [Online](https://www.statista.com/statistics/1101442/iot-number-of-connected-devices-worldwide/)
2. Coronavirus disease (COVID-19): How is it transmitted?, WHO, 2021. [Online](https://www.who.int/news-room/q-a-detail/coronavirus-disease-covid-19-how-is-it-transmitted)
3. Amazon IoT Core, [Read more](/aws.amazon.com/iot-core/)
4. AWS EC2, [Read More](https://aws.amazon.com/ec2/)
