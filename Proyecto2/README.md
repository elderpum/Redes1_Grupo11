# Proyecto #2
---------------
### Integrantes Grupo #11
|Carne | Nombre | Perfil |
|-----|-----|-----|
|201611269| Carlos Augusto Hernández Ordoñez | https://github.com/cahernao |
|201700522 | Walter Gustavo Coti Xalin | https://github.com/WalterCoti |
|201700761 | Elder Anibal Pum Rojas | https://github.com/elderpum |
|201903004 | Jonathan Alexander Alvarado Fernández  | https://github.com/jona1403 |

---------------------
# Topología #1
![Topo1](https://i.ibb.co/crWmVGn/imagen-2023-04-30-134630729.png)

## Configuración de Clouds
### Cloud 2
![Cloud2](https://i.ibb.co/9wBYw8N/imagen-2023-04-30-135328626.png)

### Cloud 3
![Cloud3](https://i.ibb.co/3SnYhgW/imagen-2023-04-30-135409666.png)

### Cloud 4
![Cloud4](https://i.ibb.co/XFJkS05/imagen-2023-04-30-135444977.png)

### Cloud 5
![Cloud5](https://i.ibb.co/64fKFbP/imagen-2023-04-30-135511305.png)

## Configuración de Routers
### Router 1
```
conf t
int f1/0
ip address 10.11.0.1 255.255.255.252
no shutdown

int f0/0
ip address 10.11.0.9 255.255.255.252
no shutdown
```

```
conf t
ip route 192.168.24.0 255.255.255.0 10.11.0.2
ip route 10.11.0.16 255.255.255.252 10.11.0.10
ip route 192.168.25.0 255.255.255.0 10.11.0.10
```

```
conf t
int f0/0
glbp 1 ip 10.11.0.10
glbp 1 preempt
glbp 1 priority 150
glbp 1 load-balancing round-robin
```

### Router 2
```
conf t
int f0/0
ip address 10.11.0.10 255.255.255.252
no shutdown

int f1/0
ip address 10.11.0.17 255.255.255.252
no shutdown
```

```
conf t
ip route 192.168.25.0 255.255.255.0 10.11.0.18
ip route 10.11.0.0 255.255.255.252 10.11.0.9
ip route 192.168.24.0 255.255.255.0 10.11.0.9
```

```
conf t
int f0/0
standby 1 ip 10.11.0.9
standby 1 priority 150
standby 1 preempt
```

### Router 3
```
conf t
int f1/0
ip address 10.11.0.5 255.255.255.252
no shutdown

int f0/0
ip address 10.11.0.13 255.255.255.252
no shutdown
```

```
conf t
int f0/0
glbp 1 ip 10.11.0.14
glbp 1 load-balancing round-robin
```

```
conf t
ip route 192.168.24.0 255.255.255.0 10.11.0.6
ip route 10.11.0.20 255.255.255.252 10.11.0.14
ip route 192.168.25.0 255.255.255.0 10.11.0.14
```

### Router 4
```
conf t
int f0/0
ip address 10.11.0.14 255.255.255.252
no shutdown

int f1/0
ip address 10.11.0.21 255.255.255.252
no shutdown
```

```
conf t
ip route 192.168.25.0 255.255.255.0 10.11.0.22
ip route 10.11.0.4 255.255.255.252 10.11.0.13
ip route 192.168.24.0 255.255.255.0 10.11.0.13
```

```
conf t
int f0/0
standby 1 ip 10.11.0.13
```

---------------------
# Topología #2
![Topo2](https://i.ibb.co/PrQ4pnw/imagen-2023-04-30-140015956.png)

## Configuración de los Cloud
### Cloud 1
![Cloud1](https://i.ibb.co/GWcS0CQ/imagen-2023-04-30-150258083.png)

### Cloud 2
![Cloud2](https://i.ibb.co/bv4qfdt/imagen-2023-04-30-150325107.png)

## Configuración de los ESW
### ESW1
```
conf t

int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/2
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/4
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

end
```

### ESW2
```
conf t

int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/2
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/4
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/5
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/6
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/7
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/8
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

end
```

### ESW3
```
conf t

int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/2
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/4
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/5
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/6
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/7
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/8
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

end
```
### ESW4
```
conf t

int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/2
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/4
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/5
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/6
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
end
``` 

## Configuración de los VTP en ESW
### ESW1
```
conf t

vtp domain redes1gp11
vtp password redes1gp11
vtp mode server

end
``` 

### ESW2
```
conf t

vtp domain redes1gp11
vtp password redes1gp11
vtp mode client

end
```

### ESW3
```
conf t

vtp domain redes1gp11
vtp password redes1gp11
vtp mode client

end
```

### ESW4
```
conf t

vtp domain redes1gp11
vtp password redes1gp11
vtp mode client

end
```

## Configuración de las VLAN
### ESW1
```
conf t 

vlan 10
name RHUMANOS
exit

vlan 20
name CONTABILIDAD
exit

vlan 30
name VENTAS
exit

vlan 40
name INFORMATICA
exit

end
```

## Configuración Port-Channel
### SW1
```
conf t

int range f1/0 -1
channel-group 2 mode on
exit

int range f1/2 -3
channel-group 1 mode on
exit

end
```

### SW2
```
conf t

int range f1/2 -3
channel-group 1 mode on
exit

int range f1/0 -1
channel-group 3 mode on
exit

int range f1/4 -6
channel-group 5 mode on
exit

end
```

### SW3
```
conf t

int range f1/0 -1
channel-group 2 mode on
exit

int range f1/2 -3
channel-group 4 mode on
exit

int range f1/4 -6
channel-group 5 mode on
exit

end
```

### SW4
```
conf t

int range f1/0 -1
channel-group 3 mode on
exit

int range f1/2 -3
channel-group 4 mode on
exit

end
```

## Configuración del STP
### SW1
```
conf t
spanning-tree vlan 10 root primary
spanning-tree vlan 20 root primary
spanning-tree vlan 30 root primary
spanning-tree vlan 40 root primary
end
```

## Configuración del Router
### R5
```
conf t
int f0/0.10
encapsulation dot1Q 10
ip address 192.168.24.62 255.255.255.192
no shutdown
exit
int f0/0.20
encapsulation dot1Q 20
ip address 192.168.24.126 255.255.255.192
no shutdown
exit
int f0/0.30
encapsulation dot1Q 30
ip address 192.168.24.190 255.255.255.192
no shutdown
exit
int f0/0.40
encapsulation dot1Q 40
ip address 192.168.24.254 255.255.255.192
no shutdown
exit
int s2/0
ip address 10.2.0.2 255.255.255.252
no shutdown
exit
int s2/1
ip address 10.2.0.6 255.255.255.252
no shutdown
end
```

```
conf t
ip route 10.2.0.8 255.255.255.252 10.2.0.1
ip route 10.2.0.12 255.255.255.252 10.2.0.5
ip route 10.2.0.16 255.255.255.252 10.2.0.1
ip route 10.2.0.20 255.255.255.252 10.2.0.5
ip route 192.168.25.0 255.255.255.0 10.2.0.1
ip route 192.168.25.0 255.255.255.0 10.2.0.5
end

```

---------------------
# Topología #3
![Topo3](https://i.ibb.co/c6N0J1y/imagen-2023-04-30-150116070.png)

## Configuración de las Cloud
### Cloud 1
![Cloud1](https://i.ibb.co/8zFKxDR/imagen-2023-04-30-150729115.png)

### Cloud 2
![Cloud2](https://i.ibb.co/Zcp2Tv8/imagen-2023-04-30-150755803.png)

## Configuración Switch VLAN
![SwitchVLAN](https://i.ibb.co/99nkgxd/imagen-2023-04-30-151102680.png)

## Configurando VLAN con las interfaces
![VLANInterfaces](https://i.ibb.co/Sw6jdGM/imagen-2023-04-30-151213468.png)

## Configurando el puerto Trunk
![Trunk](https://i.ibb.co/cFM9hw5/imagen-2023-04-30-151256767.png)

## Configuración del Router
![Router](https://i.ibb.co/TRNRHzv/imagen-2023-04-30-151350153.png)

## Configuración Router con Router
![RouterConRouter](https://i.ibb.co/cgCgKbY/imagen-2023-04-30-151517799.png)