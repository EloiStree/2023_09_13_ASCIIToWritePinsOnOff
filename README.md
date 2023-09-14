# 2023_09_13_ASCIIToWritePinsOnOff
The idea is to have a microcontroller that can turn on and off pin from a ASCII index in aim to minimized the bluetooth slow interaction.


I experimented a small problem with HC06... It is very very very slow and if you speed it up you lose data.
So with 9600 the only way to make it "fast" is to turn byte in actions instead of using text commands.
A char is 


----------------------------------------------------

```
#A1B1C1D1E1F1G1H1I1J1K1L1M1N1O1P1Q1R1S1T1U1V1W1X1
#A0B0C0D0E0F0G0H0I0J0K0L0M0N0O0P0Q0R0S0T0U0V0W0X0
#A1B1C1D1E1F1G1H1I1J1K1L1M1N1O1P1Q1R1S1T1U1V1W1X1 A0B0C0D0E0F0G0H0I0J0K0L0M0N0O0P0Q0R0S0T0U0V0W0X0
#A2B2C2D2E2F2G2H2I2J2K2L2M2N2O2P2Q2R2S2T2U2V2W2X2Y2Z2a2b2 A3B3C3D3E3F3G3H3I3J3K3L3M3N3O3P3Q3R3S3T3U3V3W3X3Y3Z3a3b3

!1 = Set all on
!0 = Set All off
A 0  tot z 51 = The pin to affect
A1 = Set Pin Registered 0 as True
A0 = Set Pin Registered 0 as False
A2 = Set G Pin 1 as True
A3 = Set G Pin 0 as False

```
