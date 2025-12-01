# Tugas-1-Jarkom_TiaraFatimahA_090
Perhitungan Base Network
NRP: 5027241090
5027241090 mod 256 = 90
Base Network: 10.90.0.0
Analisis Kebutuhan HostDari topologi

Kantor Pusat:

- Sekretariat: 380 host
- Bidang Kurikulum: 220 host
- Bidang Guru & Tendik: 95 host
- Bidang Sarana Prasarana: 45 host
- Bidang Pengawas Sekolah (Pusat): 18 host
- Server & Admin: 6 host

Kantor Cabang:
- Bidang Pengawas Sekolah (Cabang): 18 hostLink Router-to-Router:
- Link R-PUSAT ke ISR-321 (R-PUSAT): 2 host
- Link R-PUSAT ke ISR-321 (R-CABANG): 2 host
- Link ISR-321 (R-PUSAT) ke ISR-321 (R-CABANG): 2 host

Network saya: 10.90.0.0 (dari 5027241090 mod 256 = 90)
IP Assignment untuk Packet Tracer
Router S-PUSAT:

Fa0/0 (ke Sekretariat): 10.90.0.1/23
Fa0/1 (ke Kurikulum): 10.90.2.1/24
Fa0/2 (ke Guru & Tendik): 10.90.3.1/25
Fa0/3 (ke Sarpras): 10.90.3.129/26
Fa0/4 (ke Pengawas Pusat): 10.90.3.193/27
Fa0/5 (ke Server): 10.90.4.1/29
Fa1/0 (ke R-PUSAT): 10.90.4.10/30

Router R-PUSAT:

Fa0/0 (ke S-PUSAT): 10.90.4.9/30
Fa0/1 (ke ISR R-PUSAT): 10.90.4.13/30

ISR-321 R-PUSAT:

Fa0/0 (dari R-PUSAT): 10.90.4.14/30
Fa0/1 (ke ISR R-CABANG): 10.90.4.17/30

ISR-321 R-CABANG:

Fa0/0 (dari ISR R-PUSAT): 10.90.4.18/30
Fa0/1 (ke Switch Cabang): 10.90.4.21/30

Switch S-CABANG:

Vlan1 (dari ISR): 10.90.4.22/30
Interface ke Pengawas Cabang: Gateway 10.90.3.225/27

IP untuk Host/PC:

PC Sekretariat: 10.90.0.2 - 10.90.1.254 (Gateway: 10.90.0.1)
PC Kurikulum: 10.90.2.2 - 10.90.2.254 (Gateway: 10.90.2.1)
PC Guru & Tendik: 10.90.3.2 - 10.90.3.126 (Gateway: 10.90.3.1)
PC Pengawas Cabang: 10.90.3.226 - 10.90.3.254 (Gateway: 10.90.3.225)
Server: 10.90.4.2 - 10.90.4.6 (Gateway: 10.90.4.1)

Perintah Routing di Cisco:
Router R-PUSAT:
ip route 10.90.0.0 255.255.252.0 10.90.4.10
ip route 10.90.3.224 255.255.255.224 10.90.4.14

ISR R-CABANG:
ip route 0.0.0.0 0.0.0.0 10.90.4.17
