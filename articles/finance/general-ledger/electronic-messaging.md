---
title: Sistema de mensagens eletrônicas
description: Este artigo contém uma visão geral e informações de configuração de mensagens eletrônicas no Microsoft Dynamics 365 Finance.
author: AdamTrukawka
ms.date: 01/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 3e2fe6a70d449adea07f5aa0db9e625f0378d8c2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283444"
---
# <a name="electronic-messaging"></a>Sistema de mensagens eletrônicas

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral e as informações de configuração para a funcionalidade **Mensagens eletrônicas** (EM).

Recentemente, as instituições governamentais e as autoridades legislativas de vários países e regiões do mundo implementaram requisitos de relatório para as empresas registradas nesses países ou regiões. A finalidade de requisitos é habilitar os dados que devem ser obtidos das empresas no formato eletrônico, diretamente dos sistemas onde foram contabilizados, armazenados e processados.

A funcionalidade Mensagens eletrônicas do Microsoft Dynamics 365 Finance dá suporte a diversos processos de interoperação eletrônica entre o Finance e os sistemas que as autoridades governamentais e legislativas oferecem para relatórios, envios e recebimento de informações oficiais.

A funcionalidade de EM está integrada ao módulo **Relatório Eletrônico** (ER). Você pode configurar formatos de ER para mensagens eletrônicas. Para obter mais informações, consulte [Relatório eletrônico (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Conceitos básicos para funcionalidade de EM

A funcionalidade EM é baseada nas seguintes entidades:

- **Mensagem eletrônica** – Um relatório ou uma declaração que deve ser relatado ou transmitido internamente, por exemplo, um relatório enviado a um escritório de imposto.
- **Itens da mensagem eletrônica** – os registros a serem incluídos na mensagem que é relatada.
- **Processamento de mensagens eletrônicas** — Uma cadeia de ações que devem ser executadas para coletar os dados necessários, gerar relatórios, armazenar dados no Armazenamento de Blobs do Azure, transmitir relatórios para fora do sistema, receber respostas de fora do sistema e, com base nas informações recebidas, atualizar o banco de dados. As ações na cadeia podem ser vinculadas ou desvinculadas.

A ilustração a seguir mostra o fluxo de dados para EM.

![Fluxo de dados do sistema de mensagens eletrônicas.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Cenários compatíveis com a funcionalidade de EM

A funcionalidade de EM dá suporte aos seguintes cenários:

- Criar mensagens manualmente e gerar relatórios com base em formatos de ER de exportação associados de vários tipos: Esses tipos incluem Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, texto e Microsoft Word.
- Criar e processar automaticamente as mensagens baseadas em informações solicitadas e recebidas de uma autoridade usando um formato de ER de importação associado.
- Coletar e processar informações de uma fonte de dados como itens da mensagem. A fonte de dados é uma tabela do Finance.
- Armazene informações adicionais e avalie diversos valores ao chamar as classes executáveis definidas especificamente em relação a mensagens ou a itens de mensagem.
- Agregue as informações coletadas em itens de mensagem, divida essas informações por mensagem e gere relatórios que estejam em formatos de ER de exportação associados.
- Transmita os relatórios gerados para um serviço Web usando as informações de segurança armazenadas no Azure Key Vault.
- Receba uma resposta de um serviço Web, interprete a resposta e atualize os dados no Finance conforme apropriado.
- Armazene e analise todos os relatórios gerados.
- Armazene e analise todas as informações de log relacionadas a ações executadas para uma mensagem ou um item de mensagem.
- Controle o processamento entre vários status de mensagens e status de itens de mensagem.

## <a name="security-privileges"></a>Privilégios de segurança

Os privilégios de segurança a seguir estão disponíveis para mensagens eletrônicas.

| Privilégios de segurança           | Nível de acesso | Associação |
|------------------------------|--------------|-------------|
| Manter mensagens eletrônicas | Esse privilégio concede acesso total à funcionalidade de EM. Se você tiver esse privilégio, poderá configurar mensagens eletrônicas e executar todo o processamento. | Esse privilégio está incluído na obrigação de segurança **Manter transações de imposto**. Essa obrigação, por sua vez, é incluída na função de segurança **Contador**. |
| Exibir mensagens eletrônicas     | Esse privilégio concede acesso somente leitura à funcionalidade de EM. Se você tiver esse privilégio, poderá exibir as configurações de mensagens eletrônicas e as mensagens. No entanto, não é possível configurar nem executar nada. | Esse privilégio está incluído na obrigação de segurança **Consultar no status de transação do imposto**. Essa obrigação, por sua vez, é incluída nas seguintes funções de segurança.<ul><li>Gerenciador de cobranças</li><li>Auxiliar de contas a receber</li><li>Gerente de contas a receber</li><li>Contador tributário</li><li>Contador</li><li>Gerente de contabilidade</li><li>Supervisor de contabilidade</li><li>Gerente de vendas</li><li>Auxiliar de contas a pagar</li></ul> |
| Operar mensagens eletrônicas  | Esse privilégio fornece acesso somente às páginas **Mensagens eletrônicas** e **Itens de mensagens eletrônicas**. Se você tiver esse privilégio, poderá executar todo o processamento chamado nessas páginas. | Esse privilégio está incluído na obrigação de segurança **Operar mensagens eletrônicas**. Essa obrigação, por sua vez, é incluída na função de segurança **Operador de mensagens eletrônicas**. |

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Recursos regulatórios específicos do país/região para os quais a funcionalidade de EM oferece suporte

A tabela a seguir fornece informações sobre alguns recursos regulatórios específicos de país/região para os quais a funcionalidade de EM oferece suporte.

| País/Região     | Nome do recurso | Gravação de demonstração de recursos |
|-------------|--------------|------------------------|
| Espanha       | [Fornecimento imediato de informações sobre IVA (Suministro Inmediato de Información del IVA, SII)](../localizations/emea-esp-sii.md) | |
| Hungria     | [Sistema de faturamento online](../localizations/emea-hun-online-invoicing.md) | |
| Reino Unido | [Declaração de impostos digital (MTD) - Envio da declaração IVA](../localizations/emea-gbr-mtd-vat-integration.md) | [Finanças e operações: imposto digital do Reino Unido - declaração de IVA no Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Lituânia   | [Relatórios i.SAF](../localizations/emea-ltu-isaf.md) | |
| Polônia      | [Declaração de IVA com registros (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Finance: registros de auditoria de IVA SAF/JPK](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Países Baixos | [Declaração de IVA para os Países Baixos](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| República Tcheca | [Declaração de IVA](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brasil      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Rússia      | [Declaração de IVA](../localizations/rus-vat-declaration.md) | |
| Rússia      | [Relatório contábil no formato eletrônico](../localizations/rus-accounting-reporting.md) | |
| Rússia      | [Declaração de imposto sobre lucro](../localizations/rus-profit-tax-declaration.md) | |
| Rússia      | [Declaração de imposto avaliado](../localizations/rus-assessed-tax-declaration.md) | |
| Rússia      | [Declaração de imposto sobre transporte](../localizations/rus-transport-tax-declaration.md) | |
| Rússia      | [Declaração de imposto territorial](../localizations/rus-land-tax-declaration.md) | |
| Noruega      | [Restituição de IVA com envio direto para Altinn](../localizations/emea-nor-vat-return.md) | [Novo retorno de IVA com envio direto para Altinn no Dynamics 365 Finance](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/new-vat-return-with-direct-submission-to-altinn-in-dynamics-365-finance-december-1-2021) |
| França      | [Declaração de IVA (França)](../localizations/emea-fra-VAT-declaration-preview-France.md) | |
| Áustria     | [Declaração de IVA (Áustria)](../localizations/emea-aut-vat-declaration-austria.md) | |
| Alemanha     | [Declaração de IVA (Alemanha)](../localizations/emea-deu-vat-declaration-germany.md) | |
| Países Baixos | [Declaração de IVA para os Países Baixos](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Suécia      | [Declaração de IVA (Suécia)](../localizations/emea-swe-VAT-declaration-Sweden.md) | |
| Suíça | [Declaração de IVA (Suíça)](../localizations/emea-che-vat-declaration-switzerland.md) | |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]


