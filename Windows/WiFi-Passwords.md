# To view saved passwords of WiFi networks on Windows Operating Systems
---

### View All Saved Networks
```
netsh wlan show profiles
```

### See the Details of Currently connected Network
```
netsh wlan show interface
```

### View the Password of a Saved Network
```
netsh wlan show profile <network-name> key=clear 
```
<br/>

*Note: The network-name should be from the list of saved networks which would be listed if the first command to view all saved networks is run.*

<br/>

---

<br/>

*Disclaimer: This is for educational purposes only, using these knowledge to hack into someone's network is illegal and could get you into trouble.*

