# GetHMDData
��������� ��������� �������� (Yaw, Pitch, Roll) � ���������������� (X, Y, Z) �����.

```c
DWORD __stdcall GetHMDData(
	__out THMD *myHMD);
```

### ���������
myHMD [out] - ��������� �� ��������� THMD, ������� �������� ������� ��������� �����.

### ��������� THMD
```c
typedef struct _HMDData
{
	double	X;
	double	Y;
	double	Z;
	double	Yaw;
	double	Pitch;
	double	Roll;
} THMD, *PHMD;
```

���� ��� ������� ������������ ����������, ��� ����� �������� �� Yaw, Pitch, Roll.
```c
double qW, qX, qY, qZ;
qW = cos(DegToRad(yaw) * 0.5) * cos(DegToRad(roll) * 0.5) * cos(DegToRad(pitch) * 0.5) + sin(DegToRad(yaw) * 0.5) * sin(DegToRad(roll) * 0.5) * sin(DegToRad(pitch) * 0.5);
qX = cos(DegToRad(yaw) * 0.5) * sin(DegToRad(roll) * 0.5) * cos(DegToRad(pitch) * 0.5) - sin(DegToRad(yaw) * 0.5) * cos(DegToRad(roll) * 0.5) * sin(DegToRad(pitch) * 0.5);
qY = cos(DegToRad(yaw) * 0.5) * cos(DegToRad(roll) * 0.5) * sin(DegToRad(pitch) * 0.5) + sin(DegToRad(yaw) * 0.5) * sin(DegToRad(roll) * 0.5) * cos(DegToRad(pitch) * 0.5);;
qZ = sin(DegToRad(yaw) * 0.5) * cos(DegToRad(roll) * 0.5) * cos(DegToRad(pitch) * 0.5) - cos(DegToRad(yaw) * 0.5) * sin(DegToRad(roll) * 0.5) * sin(DegToRad(pitch) * 0.5);
```