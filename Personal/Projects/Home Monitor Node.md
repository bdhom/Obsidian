## Description
The Home Monitor Node (HMN) is an IoT node that monitors temperature, humidity, and light intensity. HMNs each host a Bluetooth Low Energy (BLE) GATT server in which they provide data to and receive data from the Home Monitor Hub (HMH). The HMH is responsible for hosting each node's data on a local web server.

## Take-Aways
* Start Date: first commit - 2023-05-17
* End Date: last commit - 2023-06-17

### Work Performed
* Created a BLE server that is able to relay data to connected devices (tested w/ phone)

### Accomplishments

## Tasks
- [ ] Re-familiarize self w/ code base ➕ 2023-08-05 
- [ ] Sort current changes into succinct commits ➕ 2023-08-05
- [ ] Test functionality of the current state ➕ 2023-08-05
- [ ] Connect queue manager to BLE ➕ 2023-08-05
- [ ] Setup and test I2C sensor communication ➕ 2023-08-05
- [ ] Setup system to handle notifications / upstream messages ➕ 2023-08-05
	- [ ] For interface ➕ 2023-08-05
	- [ ] For downstream ➕ 2023-08-05
	 - [ ] For BLE ➕ 2023-08-05
```C++
// notification - no ack
esp_ble_gatts_send_indicate(gattsIf, param->write.conn_id, handles[IDX_CHAR_VAL_A],
	sizeof(notifyData), notifyData, false);

// indication - ack
esp_ble_gatts_send_indicate(gattsIf, param->write.conn_id, handles[IDX_CHAR_VAL_A],
	sizeof(indicateData), indicateData, true);
```
- [ ] Handle read events for sensor device (ESP_GATT_RSP_BY_APP) ➕ 2023-08-05
- [ ] Research if performance issues for ESP_GATT_RSP_BY_APP. Possible transition to manual handling for operation service? ➕ 2023-08-05
- [ ] Setup VS Code to debug ➕ 2023-08-05
- [ ] Use NVIC to store written values ➕ 2023-08-05
- [ ] Create a rewritable config for dynamic services/characteristics ➕ 2023-08-05

## Notes
### Protocols
#### Currently Supported Protocols
* BLE (Bluetooth Low Energy)

#### NodeMCU-32S Supported Protocols
* BLE (Bluetooth Low Energy)
* Classic Bluetooth
* BLE Mesh
* CoAP (Constrained Application Protocol)
* HTTPS
* MQTT(5)
* Possibly other protocols that use TLS