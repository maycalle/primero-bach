# 4. Fundamentos lógicos de las redes

## 4.1 ¿Cómo se identifican los dispositivos en una red?

### 4.1.1 Dirección IP: qué es y por qué es necesaria



### 4.1.2 Máscara de red

### 4.1.3 Dirección de red 

Es una dirección especial que representa a toda una red. No es de un equipo, sino que identifica al conjunto de dispositivos conectados a la misma red. Se calcula usando la dirección IP del dispositivo y la máscara de red. La parte de red queda igual, y la parte de host se pone a ceros.

Ejemplo:
- IP del equipo: 192.168.1.25
- Máscara: 255.255.255.0
- Dirección de red: 192.168.1.0

Todos los equipos con IP que empiece por 192.168.1. estarán en la misma red.

### 4.1.4 Dirección de broadcast

La dirección de broadcast es una dirección IP especial que se utiliza para enviar un mensaje a todos los dispositivos de una red local al mismo tiempo.

La dirección de broadcast se obtiene tomando:
- La dirección de red (por ejemplo, 192.168.1.0)
- La máscara de red (por ejemplo, 255.255.255.0)
- Y poniendo todos los bits de la parte de host en 1 (es decir, el número más alto posible dentro de la red)

**Ejemplo:**
- *Red:* 192.168.1.0
- *Máscara de red:* 255.255.255.0 (/24). Esto significa que los últimos 8 bits son para los dispositivos (hosts).
- La dirección de broadcast será entonces: 192.168.1.255 

Eso quiere decir que si enviamos un mensaje a 192.168.1.255, todos los dispositivos con IPs desde 192.168.1.1 hasta 192.168.1.254 lo recibirán.

¡IMPORTANTE! No se debe asignar la dirección de broadcast a ningún dispositivo, porque no es un equipo, ¡es una dirección especial!


### 4.1.4 Gateway

## 4.2 Tipos de direcciones IP

### 4.2.1 Direcciones públicas y privadas

### 4.2.2 Direcciones estáticas vs dinámicas

### 4.2.3 Clases A, B y C (solo nivel básico)

### 4.2.4 Rango de IPs disponibles según la máscara