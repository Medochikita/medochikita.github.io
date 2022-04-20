- [Home](home)

# Memory read AC

 - This program read the memory of Assault Cube and prints current health and ammi in rifle <br>

 - [Repository here](https://github.com/Medochikita/Cplusplus-projects/tree/main/AssaultCube%20Health%20Memory%20Read)

offsets.h
```cpp
#pragma once

#define offsetLocalPlayer 0x6D14E8
#define Player_Health 0xEC
#define Rifle_ammo 0x140
```

main.cpp
```cpp
#include <iostream>
#include <Windows.h>
#include <TlHelp32.h>
#include <tchar.h>

#include "Header.hpp"

using std::cout;
using std::endl;

DWORD GetModuleBaseAddress(TCHAR* lpszModuleName, DWORD pID) {
	DWORD dwModuleBaseAddress = 0;
	HANDLE hSnapshot = CreateToolhelp32Snapshot(TH32CS_SNAPMODULE, pID); // make snapshot of all modules within process
	MODULEENTRY32 ModuleEntry32 = { 0 };
	ModuleEntry32.dwSize = sizeof(MODULEENTRY32);

	if (Module32First(hSnapshot, &ModuleEntry32)) //store first Module in ModuleEntry32
	{
		do {
			if (_tcscmp(ModuleEntry32.szModule, lpszModuleName) == 0) // if Found Module matches Module we look for -> done!
			{
				dwModuleBaseAddress = (DWORD)ModuleEntry32.modBaseAddr;
				break;
			}
		} while (Module32Next(hSnapshot, &ModuleEntry32)); // go through Module entries in Snapshot and store in ModuleEntry32


	}
	CloseHandle(hSnapshot);
	return dwModuleBaseAddress;
}

int main()
{
	HWND hwnd = FindWindow(NULL, "AssaultCube"); // Get the window handle

	if (hwnd == NULL)
	{
		cout << "[DEBUG]" << " No game opened" << endl;
		exit(-1);
	}

	DWORD pID = NULL;
	GetWindowThreadProcessId(hwnd, &pID); // Get the process ID

	HANDLE processHandle = NULL;

	processHandle = OpenProcess(PROCESS_ALL_ACCESS, FALSE, pID); // Opens the process for All Access and gets process handle

	if (processHandle == NULL)
	{
		cout << "[DEBUG]" << " Failed to open procces";
		exit(-1);
	}

	TCHAR game_name[] = _T("ac_client");
	DWORD gameBaseAddress = GetModuleBaseAddress(_T(game_name), pID);

	const int HealthDeadline = 500;

	for (;;) // infinite loop
	{
		DWORD PlayerHealth = (gameBaseAddress + offsetLocalPlayer) + Player_Health; // The variables need to be updated
		DWORD rifle_ammo = (gameBaseAddress + offsetLocalPlayer) + Rifle_ammo; // othervise the value wouldnt update

		ReadProcessMemory(processHandle, (LPCVOID)PlayerHealth, &PlayerHealth, sizeof(PlayerHealth), NULL);
		ReadProcessMemory(processHandle, (LPCVOID)rifle_ammo, &rifle_ammo, sizeof(rifle_ammo), NULL);
		
		if (PlayerHealth < HealthDeadline)
		{
			cout << "DANGER, ";
			cout << "Player Health: " << PlayerHealth << endl;
			cout << "Rifle ammo: " << rifle_ammo << endl;
		}
		else
		{
			cout << "Player Health: " << PlayerHealth << endl;
			cout << "Rifle ammo: " << rifle_ammo << endl;
		}

		Sleep(1000);
	}



	return 0;
}
```