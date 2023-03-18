# Proyecto #1
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
![Topo1](https://i.ibb.co/mhKXP1m/imagen-2023-03-18-050824666.png)

## ESW1
### VLANS
![T1ESW1](https://i.ibb.co/D8SGhqL/imagen-2023-03-18-051202863.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
end
```
![T1VTP1](https://i.ibb.co/27QcMkT/imagen-2023-03-18-051650130.png)

### Puertos
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
end
write
```
![T1Puertos1](https://i.ibb.co/vZj9QzH/imagen-2023-03-18-051815898.png)

## ESW2
### VLANS
![T1ESW2](https://i.ibb.co/NLTmsv3/imagen-2023-03-18-052036190.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
```
![T1VTP2](https://i.ibb.co/ZMQDwD2/imagen-2023-03-18-052219121.png)

### Puertos
```
conf t
int f1/0
switchport mode access
switchport access vlan 10
exit

int f1/1
switchport mode access
switchport access vlan 30
exit

int f1/2
switchport mode access
switchport access vlan 10
exit

int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/4
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005

end
write
```
![T1Puertos2](https://i.ibb.co/HdyVsXb/imagen-2023-03-18-052347522.png)

## ESW3
### VLANS
![T1ESW3](https://i.ibb.co/JHBjsN5/imagen-2023-03-18-052447952.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
```
![T1VTP3](https://i.ibb.co/x25t8j5/imagen-2023-03-18-052514642.png)

### Puertos
```
conf t
int f1/0
switchport mode access
switchport access vlan 20
exit

int f1/1
switchport mode access
switchport access vlan 40
exit

int f1/2
switchport mode access
switchport access vlan 30
exit

int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit

int f1/4
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005

end write
```
![T1Puertos3](https://i.ibb.co/cxLrWzx/imagen-2023-03-18-052602706.png)

----------
# Topología 2
![Topo2](https://i.ibb.co/hdwTbSS/imagen-2023-03-18-054956402.png)

## ESW4
### VLAN
```
conf t
vlan 10
name RRHH
vlan 20
name Informatica
vlan 30
name Contabilidad
vlan 40
name Ventas
```
![T2ESW4](https://i.ibb.co/yPkNXkL/imagen-2023-03-18-053454959.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp mode server
vtp version 2
```
![T2VTP4](https://i.ibb.co/KNFkXKZ/imagen-2023-03-18-053605457.png)

### Puertos
```
conf t
int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005

int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005

int f1/2
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
```
![T2Puertos4](https://i.ibb.co/jz2CYcg/imagen-2023-03-18-053636155.png)

### STP
```
spanning-tree vlan 10 root primary
spanning-tree vlan 20 root primary
spanning-tree vlan 30 root primary
spanning-tree vlan 40 root primary

write
```
![T2STP4](https://i.ibb.co/TwLskN4/ESW4-SP.png)

## ESW5
### VLAN
![T2ESW5](https://i.ibb.co/wzBS50H/imagen-2023-03-18-054130422.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
```
![T2VTP5](https://i.ibb.co/Mc4nCKK/imagen-2023-03-18-054430417.png)

### Puertos
```
int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/2
switchport mode access
switchport access vlan 20
exit
int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
end
write
```
![T2Puertos5](https://i.ibb.co/BynGD7S/imagen-2023-03-18-054451594.png)

## ESW6
### VLAN
![T2ESW6](https://i.ibb.co/QfFpT2K/imagen-2023-03-18-054551774.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
exit
```
![T2VTP6](https://i.ibb.co/Qj4GyqZ/imagen-2023-03-18-054655385.png)

### Puertos
```
int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
end
write
```
![T2Puertos6](https://i.ibb.co/C0WWWJC/imagen-2023-03-18-054715538.png)

## ESW7
### VLAN
![T2ESW7](https://i.ibb.co/1J1Rrfm/imagen-2023-03-18-054747717.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
```
![T2VTP7](https://i.ibb.co/dPDKBZC/imagen-2023-03-18-054816192.png)

### Puertos
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
end
write
```
![T2Puertos7](https://i.ibb.co/CQC0CFx/imagen-2023-03-18-054852612.png)

-----------
# Topología 3
![Topo3](https://i.ibb.co/LCgKw28/imagen-2023-03-18-055043731.png)

## ESW8
### VLAN
![T3ESW8](https://i.ibb.co/sq0V4Br/imagen-2023-03-18-055134108.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
```
![T3VTP8](https://i.ibb.co/GR56bd2/imagen-2023-03-18-055223929.png)

### Puertos
```
conf t
int f1/0
switchport mode access
switchport access vlan 40
exit
int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/2
switchport mode access
switchport access vlan 40
exit
int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
end
write

```
![T3Puertos8](https://i.ibb.co/X7pqN23/imagen-2023-03-18-055242658.png)

## ESW9
### VLAN
![T3ESW9](https://i.ibb.co/FK34m1j/imagen-2023-03-18-055306997.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
```
![T3VTP9](https://i.ibb.co/yBkCtVx/imagen-2023-03-18-055335346.png)

### Puertos
```
int f1/0
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/1
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/3
switchport mode trunk
switchport trunk allowed vlan 1,10,20,30,40,1002-1005
exit
int f1/4
switchport mode access
switchport access vlan 30
exit
int f1/5
switchport mode access
switchport access vlan 30
end
write
```
![T3Puertos9](https://i.ibb.co/MPTHd91/imagen-2023-03-18-055401771.png)

## ESW10
### VLAN
![T3ESW10](https://i.ibb.co/yYnh7dR/imagen-2023-03-18-055436642.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode client
exit
```
![T3VTP10](https://i.ibb.co/tXgWPqd/imagen-2023-03-18-055452761.png)

### Puertos
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
int f1/3
switchport mode access
switchport access vlan 10
exit
int f1/4
switchport mode access
switchport access vlan 10
end
write

```
![T3Puertos10](https://i.ibb.co/Y7xJ1Gq/imagen-2023-03-18-055524521.png)

## ESW11
### VLAN
![T3ESW11](https://i.ibb.co/Bw1v0TJ/imagen-2023-03-18-055613914.png)

### VTP
```
conf t
vtp domain GRUPO11
vtp password grupo11
vtp version 2
vtp mode transparent
exit
```
![T3VTP11](https://i.ibb.co/yXxV0Pz/imagen-2023-03-18-055633398.png)

### Puertos
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
switchport mode access
switchport access vlan 20
end
write
```

--------
# Configurar VPCs
## Topología 1
### RRHH_1
```
ip 192.168.111.10 255.255.255.0 192.168.111.1
save
```

### RRHH_2
```
ip 192.168.111.11255.255.255.0 192.168.111.1
save
```

### CONTA_1
```
ip 192.168.113.30 255.255.255.0 192.168.113.1
save
```

### CONTA_2
```
ip 192.168.113.31 255.255.255.0 192.168.113.1
save
```

### VENTAS_1
```
ip 192.168.114.40 255.255.255.0 192.168.114.1
save
```

### INFORMATICA_1
```
ip 192.168.112.20 255.255.255.0 192.168.112.1
save
```

## Topología 2
### INFORMATICA_1
```
ip 192.168.112.21 255.255.255.0 192.168.112.1
save
```

## Topología 3
### RRHH_3
```
ip 192.168.111.12 255.255.255.0 192.168.111.1
save
```

### RRHH_4
```
ip 192.168.111.13 255.255.255.0 192.168.111.1
save
```

### CONTA_3
```
ip 192.168.113.32 255.255.255.0 192.168.113.1
save
```

### CONTA_4
```
ip 192.168.113.33 255.255.255.0 192.168.113.1
save
```

### VENTAS_2
```
ip 192.168.114.41 255.255.255.0 192.168.114.1
save
```

### VENTAS_3
```
ip 192.168.114.42 255.255.255.0 192.168.114.1
save
```

### INFORMATICA_3
```
ip 192.168.112.22 255.255.255.0 192.168.112.1
save
```

-----------

# Requerimientos de GNS3
- Version **2.2.29 en adelante**
- Sistema operativo: **Windows 10 u 11**
- Imagenes IOS : **Imagen de Ethernetswitch (Switch de Capa 3)** [porporcionada por el tutor](https://drive.google.com/file/d/10810USuKu7M6s-_u6cIxek-6czPIt7XH/view)