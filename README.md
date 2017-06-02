# EPOS-Bruno

Run make_mex.m

hdl = epos_open_port('com3:    ')
epos_init(hdl)

SwitchOn
status = epos_write_object(hdl, uint16(hex2dec('6040')), uint8(0), uint8(0), uint32(hex2dec('6f')))


Shutdown
status = epos_write_object(hdl, uint16(hex2dec('6040')), uint8(0), uint8(0), uint32(hex2dec('06')))


- Position Mode:
status = epos_write_object(hdl, uint16(hex2dec('2062')), uint8(0), uint8(0), uint32(20))

- Read Position

- Operation Index:
status = epos_write_object(hdl, uint16(hex2dec('6060')), uint8(0), uint8(0), uint32(3))

Target Position:
status = epos_write_object(hdl, uint16(hex2dec('607a')), uint8(0), uint8(0), uint32(2000))


- Control:
relative position
status = epos_write_object(hdl, uint16(hex2dec('6040')), uint8(0), uint8(0), uint32(hex2dec('7f')))


Max Profile Velocity [25000 rpm]
status = epos_write_object(hdl, uint16(hex2dec('607f')), uint8(0), uint8(0), uint32(hex2dec('60')))

Profile Velocity [1000 rpm]
status = epos_write_object(hdl, uint16(hex2dec('6081')), uint8(0), uint8(0), uint32(hex2dec('60')))

Profile Accelaration [10000 rpm/s]
status = epos_write_object(hdl, uint16(hex2dec('6083')), uint8(0), uint8(0), uint32(hex2dec('60')))
