## P3.1

그림 P3.1에 스프링-질량-감쇠기 시스템이 주어져 있다.  

(a) 적당한 상태변수를 설정하라.  
(b) 상태변수로 표현된 1차 미분방정식을 구하라.  
(c) 상태미분방정식을 구하라.

<img width="2048" height="943" alt="image" src="https://github.com/user-attachments/assets/fd0a5303-1d0f-4cf7-9e2a-89b6c07a528f" />

## 상태미분방정식 유도

### (a) 주어진 식

$$
F(t) = M \frac{d^2 y(t)}{dt^2} + b \frac{d y(t)}{dt} + ky(t)
$$

이때 상태변수를 다음과 같이 정의한다.

$$
x_1(t) = y(t), \quad x_2(t) = \dot{y}(t)
$$

따라서,

$$
y(t) = x_1(t)
$$

$$
\frac{d}{dt} y(t) = x_2(t) = \frac{d}{dt} x_1(t)
$$

$$
\frac{d^2}{dt^2} y(t) = \frac{d}{dt} x_2(t)
$$

---

### (b) 상태방정식

첫 번째 방정식:

$$
\dot{x}_1(t) = x_2(t)
$$

두 번째 방정식:

$$
\dot{x}_2(t) = -\frac{k}{M} x_1(t) - \frac{b}{M} x_2(t) + \frac{1}{M} F(t)
$$

---

### (c) 상태방정식 행렬 형태

$$
\dot{X}(t) = A X(t) + B F(t)
$$

$$
X(t) =
\begin{bmatrix}
x_1(t) \\
x_2(t)
\end{bmatrix}
$$

$$
\dot{X}(t) =
\begin{bmatrix}
0 & 1 \\
-\dfrac{k}{M} & -\dfrac{b}{M}
\end{bmatrix}
X(t)
+
\begin{bmatrix}
0 \\
\dfrac{1}{M}
\end{bmatrix}
F(t)
$$

---
## P3.3

그림 P3.3과 같은 RLC 회로가 주어졌다. 상태변수  
$\( x_1(t) = i_L(t) \), \( x_2(t) = v_C(t) \)$ 로 설정하고 상태미분방정식을 구하라.

부분해답:

$$
A =
\begin{bmatrix}
0 & \dfrac{1}{L} \\
-\dfrac{1}{C} & -\dfrac{1}{RC}
\end{bmatrix}
$$

<img width="2346" height="1000" alt="image" src="https://github.com/user-attachments/assets/18cc8825-7b2f-4e1a-80c4-f987a3f3ff08" />

## 상태방정식 유도 (RLC 회로)

### ① 상태변수 정의

$$
x_1(t) = i_L(t), \quad x_2(t) = v_C(t)
$$

---

### ② 1 Node에서 KCL 적용

$$
x_1(t) = \frac{v_2(t) - x_2(t)}{R} - C \frac{d}{dt} x_2(t)
$$

---

### ③ 2 Loop에서 KVL 적용

$$
v_1(t) = L \frac{d}{dt} x_1(t) + v_2(t) - x_2(t)
$$

---

### ④ 상태변수로 표현한 1차 미분방정식

첫 번째 방정식:

$$
\frac{d}{dt} x_1(t) = \frac{1}{L} x_2(t) + \frac{1}{L} v_1(t) - \frac{1}{L} v_2(t)
$$

두 번째 방정식:

$$
\frac{d}{dt} x_2(t) = -\frac{1}{C} x_1(t) - \frac{1}{RC} x_2(t) + \frac{1}{RC} v_2(t)
$$

---

### ⑤ 상태미분방정식 (행렬형태)

$$
\dot{X}(t) = A X(t) + B V(t)
$$

$$
\dot{X}(t) =
\begin{bmatrix}
0 & \dfrac{1}{L} \\
-\dfrac{1}{C} & -\dfrac{1}{RC}
\end{bmatrix}
X(t)
+
\begin{bmatrix}
\dfrac{1}{L} & -\dfrac{1}{L} \\
0 & \dfrac{1}{RC}
\end{bmatrix}
V(t)
$$

---

## P3.5

그림 P3.5에 폐루프 제어시스템이 주어져 있다.  
(a) 폐루프 전달함수 $\( T(s) = \dfrac{Y(s)}{R(s)} \)$를 구하라.  
(b) 상태변수 모델을 구하고 위상변수형 블록선도를 작성하라.

<img width="2048" height="506" alt="image" src="https://github.com/user-attachments/assets/89515872-42f4-400c-bf45-513fae7bbcd2" />

### (a) 폐루프 전달함수 \( T(s) \) 구하기

개루프 전달함수는 다음과 같다:

$$
G(s) = \frac{s + 2}{s + 8} \cdot \frac{1}{s - 3} \cdot \frac{1}{s}
$$

이를 정리하면,

$$
G(s) = \frac{s + 2}{s (s - 3)(s + 8)}
$$

폐루프 전달함수 \( T(s) \)는 다음과 같이 표현된다:

$$
T(s) = \frac{G(s)}{1 + G(s)}
$$

따라서,

$$
T(s) = \frac{\dfrac{s + 2}{s (s - 3)(s + 8)}}{1 + \dfrac{s + 2}{s (s - 3)(s + 8)}}
$$

이를 통분하면,

$$
T(s) = \frac{s + 2}{s^3 + 5s^2 - 23s + 2}
$$

---


### (b) 상태변수 모델 유도

우선 전달함수를 다음과 같이 쓴다:

$$
T(s) = \frac{(s + 2) Z(s)}{(s^3 + 5s^2 - 23s + 2)Z(s)}
$$

즉 

$$Y(s)=sZ(s)+2Z(s)$$

$$R(s)=s^3Z(s)+5s^2Z(s)-23sZ(s)+2Z(s)$$

이를 시간영역으로 역변환하면:

$$
y(t)= \dot{z}(t) + 2 z(t) 
$$

$$
r(t)=\dddot{z}(t) + 5\ddot{z}(t) - 23\dot{z}(t) + 2 z(t) 
$$

상태변수를 다음과 같이 정의한다:

$$
x_1(t) = z(t), \quad x_2(t) = \dot{z}(t), \quad x_3(t) = \ddot{z}(t)
$$

이를 이용하면 상태방정식은:

$$
\begin{aligned}
\dot{x}_1(t) &= x_2(t) \\
\dot{x}_2(t) &= x_3(t) \\
\dot{x}_3(t) &= -5x_3(t) + 23x_2(t) - 2x_1(t) + u(t)
\end{aligned}
$$

출력 방정식은 다음과 같다:

$$
y(t) = 2x_1(t) + x_2(t)
$$

---

### (c) 상태방정식 (행렬형태)

$$
\dot{X}(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-2 & 23 & -5
\end{bmatrix}
X(t)
+
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}
u(t)
$$

출력방정식:

$$
y(t) =
\begin{bmatrix}
2 & 1 & 0
\end{bmatrix}
X(t)
$$
