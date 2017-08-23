# Motion Recognition Framework Using various sensors

## 1. **Developers**

the following is a list of developers.

1. [**Chelmin - Kim**](https://github.com/cheolmin-Kim)  **\( kcm7582@naver.com \)**

2. [**Jimin - Kim**](https://github.com/SmileJM)  **\( lovelyeu@naver.com \)**

3. [**Hwasung - Seo**](https://github.com/Marsseo)  **\( ghktjddl3@naver.com \)**

4. [**Dongju - Jang**](https://github.com/Jdongju)  **\( dj9110@naver.com\)**

## 2. Overview

It is Motion framework for remote control of drones, rovers, and various IoT devices in motion using sensor values.

센서값을 이용하여 모션으로 드론, 로버, 각종 IoT 장치를 원격 제어할 수 있는 모션 프레임워크

This framework has the following advantages.

1. 손쉽게 임베디드 장치와 CoAP 통신을 할 수 있는 환경을 제공한다.

2. 모션 인식 개발에 활용 가능한 알고리즘이 포함되어 있다.

3. 모션 프레임워크를 이용하는 사용자를 위해 Tutorial이 만들어져 있으며 Javadoc을 홈페이지에 기재 하여 놓았다.

4. 사용자의 환경에 맞게 조건을 변경하여 사용 가능 하도록 하였고 Overriding하여 직접 모션 알고리즘을 넣을 수 있도록 하였다.

5. Gyroscope Sensor의 특성상 yaw축에 Drift 현상이 발생하는데, 이럴 경우에도 모션인식이 가능하도록 솔루션을 제공한다.

6. 해당 프레임 워크의 전용 홈페이지를 개설하여 모션 인식 관련한 활발한 커뮤니티가 이루어 질 수 있도록 하였다.

7. 웹 사이트에서 클라이언트인 임베디드 장치에 연결된 센서들의 현재 상태를 체크 해볼 수 있도록 해준다.

## 3. What is this?

#### **▶ 설명**

It is Motion framework for remote control of drones, rovers, and various IoT devices in motion using sensor values.

This framework basically enables motion recognition using values of gyroscope sensor, ultrasonic sensor, acceleration sensor, infrared sensor, and button sensor.

* Motion recognition using axis values.

![](http://blogfiles8.naver.net/MjAxNzA4MjBfMTU5/MDAxNTAzMTYwMTExNTk4.mWaDX1DZ4RmC70xyFR3iSviHcJFThplv7dVib9UiT9kg.wCmswrKRV5WMpa9tKij9jbQLWg6Pp21-46BzD-cPnqMg.PNG.sword97/yaw.png)

임베디드 장치에서 자이로센서와 가속도 센서를 활용하여 yaw축 , pitch축, roll축의 현재 각도만 실시간으로 전송해 주면 우리 프레임워크를 사용하여 개발한 Server측에서 모션을 인식할 수 있다. 만약 자이로스코프와 가속도 센서를 사용하여 계산해 낸 각도를 활용한 모션인식을 하고자 한다면 모션 트리거가 되어 줄 적어도 하나 이상의 다른 센서가 필요하다. 모션 트리거는 모션 행동의 시작과 끝을 알려주는 기능을 한다. 다른 센서가 모션 트리거가 되어 트리거가 On되고 Off되는 시점 사이에 취해진 모션이 인식 되어진다.

* Motion recognition using distance values.

센서로 측정한 거리를 우리 프레임 워크를 사용하여 개발한 Server 측으로 전송해 주게 되면 거리 값에 따라 이벤트를 줄 수 있도록 하였다. 거리를 측정하기 위해 사용될 수 있는 센서는 초음파 센서 , 적외선 센서 등이 있다

* Motion recognition using On / off status

센서의 On/ Off 상태를 프레임 워크를 사용하여 개발한 Server 측으로 String으로 전송해 주게 되면 상태 값에 따라 이벤트를 줄 수 있도록 하였다. 상태를 측정하기 위해 사용될 수 있는 센서는 터치 센서 , 버튼 센서 등이 있다.

#### ▶ 프로세스

이 프레임 워크의 동작 프로세스는 3단계로 나누어 집니다.

* 1단계는 모션 트리거가 되지 않은 상태입니다.

* 2단계는 모션 트리거가 On 되어진 상태 입니다.

* 3단계는 모션 트리거가 Off 되어지고 인식된 모션의 결과가 나오는 단계입니다.

## 4. Usage

#### ▶ 사용 준비

![](/assets/cap.PNG)

위의 그림과 같이 임베디드 장치를 손이나 팔 위에 올려놓고 팔을 앞으로 뻗었을 때를 기본 상태로 간주한다. 해당 상태가 되었을 때 yaw축 , roll축 , pitch축 각각은 180도가 되도록 하고 각각의 각의 범위는 0도에서 360도가 되도록 클라이언트에서 셋팅하여 서버로 값을 전송해야 한다. yaw축은 0도에서 360도 까지의 범위만 유지하고 정확히 180도가 되지 않더라도 모션 인식이 동작하는데 무리 없도록 하는 솔루션을 제공한다. 따라서 yaw축에 Drift 현상이 발생 하더라도 모션을 인식하는 것에 큰 지장을 주지 않도록 하였다.

클라이언트에서 전송하는 각각의 값은 서로에게 영향을 주지 않고 독립적인 상태였을 때 가장 이상적인 모션 인식 알고리즘을 만들 수 있다. 따라서 클라이언트 측에서 되도록 신경써서 값을 독립적이며 정확하게 보내 주도록 하는 것을 권장한다.

프레임 워크에서는 CoAP 통신이 가능하도록 Server 환경이 갖추어져 있으며 따라서 클라이언트 측에서는 해당 리소스로 3축의 값을 전송만 해주면 된다.

3축의 값을 전송받는 리소스 이름은 gyroscope 이며 post 방식으로 {"sensor":"gyroscope","yawAngle":"value","pitchAngle":"value","rollAngle":"value"}  라는 Json 형태의 데이터를 보내줘야 한다.

또한 , post방식으로 쿼리 스트링 형태로 데이터를 전송 해도 된다.

sensor=gyroscope&yawAngle=value&pitchAngle=value&rollAngle=value 와 같이 각 축의 value 값을 보내줘야 한다.





위의 코드는 CoAP Server측에 등록되어 있는 리소스의 이름이고 

우리 Repository의 Client4MR 프로젝트는 테스트를 위해 임베디드 장치에서 CoAP 클라이언트 부분으로 서버에 값을 전송







우리의 프레임 워크는 CoAP 통신을 간단한 코드로 구현 가능하도록 해준다.



## 5. Requirements

## 6. Download



