## Progress
[Unread] 5.3: too rough
[TBR] 5.4/A.1/


## Concepts and abbreviations
TSG (Technical Specification Group): 
- include 3 main TSGs
    - TSG RAN（Radio Access Network）
    - TSG SA（Service and System Aspects）
    - TSG CT（Core Network and Terminals）
- each TSG contains several WG (Working Group)

UE (User Equipment)

EPS (Evolved Packet System)
- E-UTRAN
- evolved packet core network

NAS (Non-access Stratum)
- EMM (EPS Mobility Management)
- ESM (EPS Session Management)

5GMM (5G Mobility Management)

RAN (Radio Access Network)
- GERAN (GSM EDGE Radio Access Network): 2.5G / 2.75G
- UTRAN (UMTS Terrestrial Radio Access Network): 3G
- E-UTRAN (Evolved UMTS Terrestrial Radio Access Network): LTE
- NG-RAN (Next Generation Radio Access Network): 5G

RLOS (Restricted Local Operator Services)

PLMN (Public Land Mobile Network)
- MCC (Mobile Country Code)
- MNC (Mobile Network Code)

MNO (Mobile Network Operator)

CSG (Closed Subscriber Group)

SAE (System Architecture Evolution)

GBR (guaranteed bit rate)

PDP（Policy Decision Point） Context
- PDN Gateway (Packet Data Network Gateway)
- APN (Access Point Name)

5G-GUTI (Globally Unique Temporary UE Identity)

MME (Mobility Management Entity): a control point in the EPS
- EMM is not a physical instance but a function set

GUMMEI (Globally Unique MME Identifier)

P-TMSI (Packet Temporary Mobile Subscriber Identity): 2G/3G

IMSI（International Mobile Subscriber Identity）

AMF (Access and Mobility Management Function): 5G

or AMF (Authentication management field)


SMS (Short Message Service)

AKA (Authentication and Key Agreement)

AUTN (authentication token):
- Used by the UE to verify the authenticity of the network. 
- This includes a sequence number (SQN) and an authentication management field (AMF), both encrypted and integrity-protected using the operator-specific key K.

AMBR (Aggregate Maximum Bit Rate)

eNode B (Evolved Node B)

EPC (Evolved Packet Core Network): LTE

HeNB (Home eNode B)

IP-CAN (IP-Connectivity Access Network)

KSI (Key Set Identifier)

TMSI (Temporary Mobile Subscriber Identity)

ICV (Integrity Check Value):
- a broader concept than MAC
- to check whether the content is altered (may involve no key)

MAC (Message Authentication Code)
- stored in AUTN

TA (Tracking Area)

TAC (Tracking Area Code)

TAI (Tracking Area Identity)
- The TAI list contains a list of Tracking Areas (TAs) that a User Equipment (UE) can move between without needing to perform a tracking area update each time it changes TA.

V2X (Vehicle-to-Everything)

IMS（IP Multimedia Subsystem）

K_{ASME}（Authentication and Security Management Key for EPC）

EIA0（EPS Integrity Algorithm 0）:integrity algorithm used for emergency service

PSM (Power Saving Mode)

ISR (Idle State Relocation):
- The key aspect of ISR is to preserve the UE's context both in the old network (previous serving network) and the new network (target serving network) for a certain period, even when the device is in an idle state.

Network interfaces
- Lu: 3G UMTS (RNC (Radio Network Controller) and (MSC or MGCF in CN))
- S1: LTE (eNode B and (MME and S-GW in CN))
- A/Gb
    - A: GSM (BSS and MSC): for voice
    - Gb: GPRS (BSS and SGSN): for data transmission
- N1: 5G NR (UE and AMF): NAS messages
- N2: 5G NR (gNodeB and AMF)

GSM (Global System for Mobile Communication): 2G

GPRS (General Packet Radio Service): 2.5G

UMTS (Universal Mobile Telecommunications System): 3G

eCall: emergency-related

USIM (Universal Subscriber Identity Module)

MUSIM (Multiple USIM)

IE (Information Elements)

CSFB (Circuit Switched Fallback) 

TIN (Type of Identity)

RAT (Radio Access Technology)

S-TMSI（Security Temporary Mobile Subscriber Identity）

P-TMSI（Public Temporary Mobile Subscriber Identity）

IAB-node (Integrated Access and Backhaul node)

DCN-ID (Data Communication Network Identifier)

UICC (Universal Integrated Circuit Card)

S101 mode: seamless switch between 3GPP and non-3GPP

RACS: UE Radio Capability Signaling Optimization

eDRX (Extended Discontinuous Reception)

eKSI (extended Key Set Identifier)

MANET (Mobile ad hoc Network)

RAND (Random Challenge)

RES (Response)

N26 interface: switch between 4G and 5G

DRX (Discontinuous Reception) parameter
- relates to how a UE handles power-saving features while maintaining connectivity

Wake-Up Signal (WUS) assistance
- help UE save power by reducing unnecessary radio wake-ups


Single-registration mode
- allows a UE to be registered on a single network at a time. This contrasts with dual-registration mode, where a device can maintain simultaneous registrations with more than one network generation—such as 4G LTE and 5G NR (New Radio).