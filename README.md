真实稀有小马拉大车视频_45

 // RTU  
 SerialPort serialPort = new SerialPort("COM2", 9600, Parity.None, 8, StopBits.One);
 serialPort.Open();
 ModbusMaster master = ModbusSerialMaster.CreateRtu(serialPort);

 // 起始地址    “40001”      "I0.0"    "DB1.DBW100"
 ushort[] values = master.ReadHoldingRegisters(1, 0, 2);

 // 功能    效率

 // float数据   从两个ushort值转换成float


 // 设置从设备地址和要写入的寄存器地址及值  
 ushort startAddress = 0; // 起始地址  
 ushort valueToWrite = 123; // 要写入的寄存器值  

 // 将值写入从设备的寄存器中  
 master.WriteSingleRegister(1, startAddress, valueToWrite);
