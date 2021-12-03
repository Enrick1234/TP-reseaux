Vlan 10 = Finance
Vlan 20 = Manufacture
Vlan 30 = RH
Vlan 40 = Direction
Vlan 50 = Serveur

**Switchs :**

- Access_1 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Access_1
Access_1(config)#vlan 10
Access_1(config-vlan)#name Finance
Access_1(config-vlan)#exit
Access_1(config)#int fa0/1
Access_1(config-if)#sw access vlan 10
Access_1(config)#int fa0/2
Access_1(config-if)#sw access vlan 10

Access_1(config)#int fa0/24
Access_1(config-if)#switchport mode trunk
Access_1(config-if)#switchport trunk allowed vlan 10
Access_1(config-if)#no shutdown
Access_1(config-if)#exit
Access_1(config)#exit
Access_1#
```

- Access_2 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Access_2
Access_2(config)#vlan 30
Access_2(config-vlan)#name RH
Access_2(config-vlan)#exit
Access_2(config)#vlan 20
Access_2(config-vlan)#name Manufacture
Access_2(config-vlan)#exit
Access_2(config)#int fa0/1
Access_2(config-if)#sw access vlan 30
Access_2(config)#int fa0/2
Access_2(config-if)#sw access vlan 20

Access_2(config)#int fa0/24
Access_2(config-if)#switchport mode trunk
Access_2(config-if)#switchport trunk allowed vlan 20,30
Access_2(config-if)#no shutdown
Access_2(config-if)#exit
Access_2(config)#exit
Access_2#
```

- Access_3 : 

```
Switch>en
Switch#conf t
Switch(config)#hostname Access_3
Access_3(config)#vlan 30
Access_3(config-vlan)#name RH
Access_3(config-vlan)#exit
Access_3(config)#vlan 20
Access_3(config-vlan)#name Manufacture
Access_3(config-vlan)#exit
Access_3(config)#int fa0/1
Access_3(config-if)#sw access vlan 30
Access_3(config)#int fa0/2
Access_3(config-if)#sw access vlan 20

Access_3(config)#int fa0/24
Access_3(config-if)#switchport mode trunk
Access_3(config-if)#switchport trunk allowed vlan 20,30
Access_3(config-if)#no shutdown
Access_3(config-if)#exit
Access_3(config)#exit
Access_3#
```

- Access_4 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Access_4
Access_4(config)#vlan 20
Access_4(config-vlan)#name Manufacture
Access_4(config-vlan)#exit
Access_4(config)#int fa0/1
Access_4(config-if)#sw access vlan 20
Access_4(config)#int fa0/2
Access_4(config-if)#sw access vlan 20

Access_4(config)#int fa0/24
Access_4(config-if)#switchport mode trunk
Access_4(config-if)#switchport trunk allowed vlan 20
Access_4(config-if)#no shutdown
Access_4(config-if)#exit
Access_4(config)#exit
Access_4#
```

- Access_5 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Access_5
Access_5(config)#vlan 10
Access_5(config-vlan)#name Finance
Access_5(config-vlan)#exit
Access_5(config)#vlan 40
Access_5(config-vlan)#name Direction
Access_5(config-vlan)#exit
Access_5(config)#int fa0/1
Access_5(config-if)#sw access vlan 10
Access_5(config)#int fa0/2
Access_5(config-if)#sw access vlan 40

Access_5(config)#int fa0/24
Access_5(config-if)#switchport mode trunk
Access_5(config-if)#switchport trunk allowed vlan 10,40
Access_5(config-if)#no shutdown
Access_5(config-if)#exit
Access_5(config)#exit
Access_5#
```

- Access_6 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Access_6
Access_6(config)#vlan 50
Access_6(config-vlan)#name Serveur
Access_6(config-vlan)#exit
Access_6(config)#int fa0/1
Access_6(config-if)#sw access vlan 50

Access_6(config)#int fa0/24
Access_6(config-if)#switchport mode trunk
Access_6(config-if)#switchport trunk allowed vlan 50
Access_6(config-if)#no shutdown
Access_6(config-if)#exit
Access_6(config)#exit
Access_6#
```


- Distrib_1 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Distrib_1
Distrib_1(config)#int fa0/24
Distrib_1(config-if)#switchport mode trunk
Distrib_1(config-if)#switchport trunk allowed vlan 10
Distrib_1(config-if)#no shutdown
Distrib_1(config-if)#exit

Distrib_1(config)#int fa0/23
Distrib_1(config-if)#switchport mode trunk
Distrib_1(config-if)#switchport trunk allowed vlan 20,30
Distrib_1(config-if)#no shutdown
Distrib_1(config-if)#exit

Distrib_1(config)#int fa0/22
Distrib_1(config-if)#switchport mode trunk
Distrib_1(config-if)#switchport trunk allowed vlan 20,30
Distrib_1(config-if)#no shutdown
Distrib_1(config-if)#exit

Distrib_1(config)#exit
Distrib_1#
```

- Distrib_2 :

```
Switch>en
Switch#conf t
Switch(config)#hostname Distrib_2
Distrib_2(config)#int fa0/24
Distrib_2(config-if)#switchport mode trunk
Distrib_2(config-if)#switchport trunk allowed vlan 10,40
Distrib_2(config-if)#no shutdown
Distrib_2(config-if)#exit

Distrib_2(config)#int fa0/23
Distrib_2(config-if)#switchport mode trunk
Distrib_2(config-if)#switchport trunk allowed vlan 50
Distrib_2(config-if)#no shutdown
Distrib_2(config-if)#exit

Distrib_2(config)#exit
Distrib_2#
```

- Coeur : 

```
Switch>en
Switch#conf t
Switch(config)#hostname Coeur
Coeur(config)#int fa0/24
Coeur(config-if)#switchport mode trunk
Coeur(config-if)#switchport trunk allowed vlan 10,20,30
Coeur(config-if)#no shutdown
Coeur(config-if)#exit

Coeur(config)#int fa0/23
Coeur(config-if)#switchport mode trunk
Coeur(config-if)#switchport trunk allowed vlan 20
Coeur(config-if)#no shutdown
Coeur(config-if)#exit

Coeur(config)#int fa0/22
Coeur(config-if)#switchport mode trunk
Coeur(config-if)#switchport trunk allowed vlan 10,40,50
Coeur(config-if)#no shutdown
Coeur(config-if)#exit

Coeur(config)#exit
Coeur#
```

**Routeur :**

- R1