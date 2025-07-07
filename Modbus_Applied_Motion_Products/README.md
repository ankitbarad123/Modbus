## Example of Modbus Protocol with Applied Motion Products devices
- MDX+ Integrated Servo Motor with Modbus TCP 
- Reading and Writing Holding Registers

--- 

## Important note:- 
- When communicating Modbus devices with PLC, user need to make sure that the mapping for PLC/HMI holding register 40001 to Applied Motion device 40000. 
- Applied Motion Modbus devices Holding register start from 40000 where many PLC/HMI use 40001 as the first holding register address.

---

## Testing with CODESYS Software for reading and writing holding registers
![image](https://github.com/user-attachments/assets/e11c1ca6-7cc2-42db-920e-db865ac1c884)


