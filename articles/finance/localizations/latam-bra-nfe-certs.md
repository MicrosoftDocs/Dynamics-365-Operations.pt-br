---
title: Certificados de NF-e
description: Este tópico fornece informações sobre certificados de NF-e para o Microsoft Dynamics 365 Finance e a solução que você deve usar para cada autoridade fiscal estadual.
author: sndray
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, EcoResProductDetails, LogisticsAddressSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 81e7598e0d4c12c07e2f12a7bb9f39bc1e4d5fcf29e5d8096350d39c45df186b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732920"
---
# <a name="nf-e-certificates"></a>Certificados de NF-e

[!include [banner](../includes/banner.md)]

Na localização brasileira, você deve gerar uma Nota Fiscal eletrônica (NF-e) para registrar a movimentação de itens e serviços entre duas partes.
O documento fiscal NF-e deve ser assinado e transmitido à autoridade fiscal do estado usando um certificado de cliente que é emitido por uma autoridade de certificação (CA) brasileira.
Antes de gerar uma NF-e, você deve concluir as seguintes tarefas:
- Configurar serviços Web, códigos de rejeição e esquemas.
- Para cada estabelecimento fiscal, configure:

    - O certificado do cliente
    - Um ambiente
    - Uma versão da NF-e
    - Uma autoridade
    - Um modelo
    - Validação de esquema
    - Um modo de contingência para NF-e
    
- Configure a impressão automática do Documento auxiliar da Nota fiscal eletrônica (DANFE), de forma que o DANFE seja impresso automaticamente após a aprovação da NF-e.
- Configure os serviços da Web relacionados a uma autoridade fiscal.
- Configurar um tipo de documento fiscal para NF-e.

## <a name="set-up-certificates"></a>Configurar certificados
O processo usado para instalar certificados varia, dependendo do estado onde a nota fiscal de NF-e é emitida. Use o processo de instalação de certificado correto para que o Dynamics 365 Finance possa se conectar aos serviços Web do estado.

O governo brasileiro atualizou a autoridade de certificação (CA) raiz usada para emitir o certificado necessário para estabelecer uma conexão de protocolo SSL (Secure Sockets Layer) no servidor. A versão atual da AC Raiz é a v5. Por padrão, a versão anterior (AC Raiz v2) é implantada no Microsoft Windows.

## <a name="solutions"></a>Soluções
- Instalar manualmente a AC Raiz v5 – o certificado raiz deve ser instalado na loja Autoridades de certificação raiz confiáveis. Embora o governo brasileiro tenha criado um novo certificado raiz (v5), a Segurança do Windows ainda não adicionou esse certificado à loja Autoridades de certificação raiz confiáveis. Isso significa que você deverá abrir um incidente no Suporte do Windows e, em seguida, instalar manualmente o certificado. Você pode usar essa solução alternativa até que o grupo de Segurança do Windows chegue a um acordo com o governo brasileiro.
- Instalar o proxy de NF-e em uma VM local – as autoridades fiscais dos estados do Ceará (CE), de Goiás (GO) e de Pernambuco (PE) não habilitaram o protocolo mais seguro e padrão de mercado, Transport Layer Security (TLS) 1.2, em seus servidores Web. No entanto, as máquinas virtuais (VMs) do Windows usadas para executar o Finance seguem a política de segurança da Microsoft e permitem apenas conexões que usam TLS 1.2. Portanto, o sistema não pode conectar-se diretamente a esses serviços Web. Para expedir comunicações a esses três estados, os clientes devem instalar um serviço Web de proxy em uma VM do Windows local em sua assinatura do Microsoft Azure.

Certificados brasileiros devem ser instalados por meio do Azure Key Vault. O Key Vault permite armazenar chaves de criptografia, certificados e segredos (como chaves de autenticação, chaves da conta de armazenamento, chaves de criptografia de dados, arquivos .pxf e senhas) usando chaves protegidas por módulos de segurança de hardware (HSMs).

Para obter mais informações sobre como usar chaves e segredos com o Key Vault, consulte [Sobre chaves, segredos e certificados](/rest/api/keyvault/about-keys--secrets-and-certificates).
A tabela a seguir lista todas as autoridades fiscais e as soluções que você deve usar para instalar certificados para elas.

|Autoridade fiscal| Estados| Solução|
|-------------|-------|---------|
|Sefaz Amazonas (AM)| AM| Instalar manualmente a AC Raiz v5.|
|Sefaz Bahia (BA)|  BA| Instalar manualmente a AC Raiz v5.|
|Sefaz Ceará (CE)|  CE| Instalar o proxy de NF-e em uma VM local.|
|Sefaz Goiás (GO)|  GO| Instalar o proxy de NF-e em uma VM local.|
|Sefaz Minas Gerais (MG)|   MG| Instalar manualmente a AC Raiz v5.|
|Sefaz Mato Grosso do Sul (MS)| MS| Nenhuma solução adicional é necessária|
|Sefaz Mato Grosso (MT)|    MT| Nenhuma solução adicional é necessária|
|Sefaz Pernambuco (PE)| PE| Instalar o proxy de NF-e em uma VM local.|
|Sefaz Paraná (PR)| PR| Instalar manualmente a AC Raiz v5.|
|Sefaz Rio Grande do Sul (RS)|  RS| Nenhuma solução adicional é necessária|
|Sefaz São Paulo (SP)|  SP| Nenhuma solução adicional é necessária|
|Sefaz Virtual Ambiente Nacional (SVAN)|    MA, PA| Nenhuma solução adicional é necessária|
|Sefaz Virtual Rio Grande do Sul (SVRS)|    AC, AL, AP, DF, ES, PB, PI, RJ, RN, RO, RR, SC, SE, TO| Nenhuma solução adicional é necessária|

### <a name="contingency-authorization-authorities-used-when-the-authority-is-down-or-offline"></a>Autoridades de autorização de contingência (usadas quando a autoridade estiver fora do ar ou offline)

|Autoridade fiscal| Estados| Solução|
|-------------|-------|---------|
|Sefaz Virtual de Contingência Ambiente Nacional (SVC-AN)|  AC, AL, AP, DF, ES, MG, PB, RJ, RN, RO, RR, RS, SC, SE, SP, TO| Instalar manualmente a AC Raiz v5.|
Sefaz Virtual de Contingência Rio Grande do Sul (SVC-RS)|   AM, BA, CE, GO, MA, MS, MT, PA, PE, PI, PR| Nenhuma solução adicional é necessária|




[!INCLUDE[footer-include](../../includes/footer-banner.md)]