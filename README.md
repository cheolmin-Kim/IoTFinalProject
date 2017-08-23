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

3. 모션 프레임워크를 이용하는 사용자를 위해 Javadoc을 홈페이지에 기재 하여 놓았다.

4. 사용자의 환경에 맞게 조건을 변경 가능 하도록 하였으며 , Overriding하여 직접 모션 알고리즘을 넣을 수 있도록 하였다.

5. 웹 사이트에서 클라이언트인 임베디드 장치에 연결된 센서들의 현재 상태를 체크 해볼 수 있도록 해준다.

## 3. What is this?

It is Motion framework for remote control of drones, rovers, and various IoT devices in motion using sensor values.

This framework basically enables motion recognition using values of gyroscope sensor, ultrasonic sensor, acceleration sensor, infrared sensor, and button sensor.

1. Motion recognition using axis values.

![](http://blogfiles8.naver.net/MjAxNzA4MjBfMTU5/MDAxNTAzMTYwMTExNTk4.mWaDX1DZ4RmC70xyFR3iSviHcJFThplv7dVib9UiT9kg.wCmswrKRV5WMpa9tKij9jbQLWg6Pp21-46BzD-cPnqMg.PNG.sword97/yaw.png)

If you want to use motion recognition with a gyroscope sensor, you need at least one other sensor to turn the motion trigger on and off.

임베디드 장치에서 자이로센서와 가속도 센서를 활용하여 yaw축 , pitch축, roll축의 현재 각도만 실시간으로 전송해 주면 우리 프레임워크를 사용하여 개발한 Server측에서 모션을 인식할 수 있다. 만약 자이로스코프와 가속도 센서를 사용하여 계산해 낸 각도를 활용한 모션인식을 하고자 한다면 모션 트리거가 되어 줄 적어도 하나 이상의 다른 센서가 필요하다. 모션 트리거는 모션 행동의 시작과 끝을 알려주는 기능을 한다. 다른 센서가 모션 트리거가 되어 트리거가 On되고 Off되는 시점 사이에 취해진 모션이 인식 되어진다.

   2. Motion recognition using distance values.

센서로 측정한 거리를 우리 프레임 워크를 사용하여 개발한 Server 측으로 전송해 주게 되면 거리 값에 따라 이벤트를 줄 수 있도록 하였다. 거리를 측정하기 위해 사용될 수 있는 센서는 초음파 센서 , 적외선 센서 등이 있다.

    3. Motion recognition using On / off status

센서의 On/ Off 상태를 프레임 워크를 사용하여 개발한 Server 측으로 전송해 주게 되면 거리 값에 따라 이벤트를 줄 수 있도록 하였다. 거리를 측정하기 위해 사용될 수 있는 센서는 터치 센서 , 버튼 센서 등이 있다.

## 4. Usage

## 5. Requirements

## 6. Download



