# Caso Real: Phishing UAC 2026 - Credential Harvesting

**Fecha:** 10/10/2026
**Víctima:** luis.ospino3@uac.edu.co
**Urgencia SOC:** 2 - ALTA
**TTPs MITRE:** T1566.002 (Phishing Link), T1078, T1585.001 (Establish Accounts - Wix)

## Análisis
- Correo con logo oficial UAC + pretexto "cuenta programada para ser eliminada"
- Ingeniería social: Fecha límite 01/09/2026 = presión
- Link malicioso: https://cuentainstituciona5[.]wixsite.com/login
- Infraestructura: Wixsite.com (legítimo) abusado para hosting de phishing

## IoCs
- URL: cuentainstituciona5.wixsite.com/login
- Dominio base: wixsite.com (abusado)
- Keyword: cuentainstituciona5

## Validación Sandbox
- URLScan / VirusTotal: Marcar como phishing
- No descargar, solo credential harvesting

## Mitigación
1. Bloqueo en proxy/firewall: *.wixsite.com/login con keywords institucionales
2. Reportar a Wix Abuse: abuse@wix.com
3. Reset de contraseña si se dio click
4. Regla Sentinel abajo

## Referencias MITRE ATT&CK
- T1566.002 Phishing: Spearphishing Link: https://attack.mitre.org/techniques/T1566/002/
- T1078 Valid Accounts: https://attack.mitre.org/techniques/T1078/
- T1585.001 Establish Accounts: Social Media Accounts: https://attack.mitre.org/techniques/T1585/001/
