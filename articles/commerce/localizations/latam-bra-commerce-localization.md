---
title: Localização do Commerce para o Brasil
description: Este tópico fornece uma visão geral da localização do Microsoft Dynamics 365 Commerce para o Brasil.
author: josaw
ms.date: 05/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: v-ankvik
ms.search.validFrom: 2020-8-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4d9f278838fafbd40155ab212cf8c7dcb46d6d3a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020273"
---
# <a name="commerce-localization-for-brazil"></a>Localização do Commerce para o Brasil

[!include[banner](../includes/banner.md)]

Este tópico descreve o escopo da funcionalidade do Microsoft Dynamics 365 Commerce específico do Brasil. Ele inclui informações sobre os recursos e a funcionalidade que foram criados para tratar impostos federais específicos, de varejo, contábeis, financeiros ou estatutários ou regulamentações que geralmente afetam as empresas de varejo no Brasil (no escopo da [Localização Brasileira](../../finance/localizations/latam-bra-scope.md#brazilian-localization-strategy)).

Porém, o Commerce não trata de todas as leis, regulamentos ou requisitos comerciais do Brasil, pois as leis e os regulamentos variam na forma como afetam as organizações. Para obter mais informações, consulte o [Guia de disponibilidade de tradução e localização de produtos](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="capabilities-of-the-commerce-localization-for-brazil"></a>Recursos da localização do Commerce para o Brasil

### <a name="scope-that-is-available-in-brazil"></a>Escopo disponível no Brasil

Os seguintes recursos do Commerce headquarters e do ponto de venda (PDV) estão disponíveis para clientes do Commerce no Brasil:

- Gerenciamento de produtos de varejo e cálculo de impostos específicos do Brasil aplicáveis a vendas para consumidores finais. Esse recurso inclui um detalhamento de imposto estimado em recibos fiscais impressos.
- Geração de documentos fiscais eletrônicos da Nota Fiscal do Consumidor eletrônica - NFC-e para vendas de varejo (modelo 65), envio dos documentos fiscais eletrônicos por meio dos serviços Web do governo e impressão dos recibos de DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) NFC-e.
- Cancelamento de vendas de varejo por meio dos serviços Web do governo no prazo permitido.
- Geração de documentos fiscais eletrônicos da NF-e (Nota Fiscal eletrônica) para devoluções de varejo (modelo 55), envio de documentos fiscais eletrônicos por meio dos serviços Web do governo e impressão dos recibos DANFE.
- Geração de documentos fiscais eletrônicos do CF-e (Cupom Fiscal eletrônico) para vendas de varejo em São Paulo (modelo 59) e registro de documentos fiscais eletrônicos no dispositivo fiscal SAT (Sistema Autenticador e Transmissor de Cupons Fiscais Eletrônicos).
- Integração de transferência eletrônica de fundos (TEF) para o PDV. Esse recurso inclui integração com provedores de pagamento locais e globais populares, e suporte para pagamentos com cartão de crédito e débito.
- Gerenciamento de números de registro de clientes específicos do Brasil. Esse recurso inclui recursos para inserir, exibir e modificar os números de registro de impostos do CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas) ou IDs de Estrangeiro, e para registrar esses números em NFC-e, NF-e, CF-e e em recibos impressos.
- Registro adiado de documentos fiscais eletrônicos, no caso de falhas de rede (modo de contingência offline) e a transmissão subsequente de documentos fiscais eletrônicos na contingência do Commerce headquarters.
- Controle de documentos fiscais eletrônicos no Commerce headquarters. Esse recurso inclui recursos para descartar os documentos e registrar um cancelamento por substituição.
- Geração e envio de documentos fiscais eletrônicos para ordens de clientes.
- A capacidade de emitir NF-e vinculada para todos os tipos de documentos fiscais registrados.
- Suporte de N-1, para que os clientes que executam o Microsoft Dynamics AX 2012 R3 em suas lojas possam trabalhar com a sede do Microsoft Dynamics 365 Commerce após uma atualização.
- Suporte para campos específicos do Brasil, como números de registro de impostos do CNPJ/CPF, quando os registros do cliente principais forem mesclados em um call center.

### <a name="supported-scenarios"></a>Cenários com suporte

Os cenários a seguir têm suporte da localização do Commerce para o Brasil:

- Vendas de mercadorias por cash-and-carry
- Cancelamentos e devoluções de vendas de mercadorias por cash-and-carry
- Vendas de mercadorias por cash-and-carry no modo de contingência offline
- Cancelamento por substituição
- Emissão de vales-presentes e pagamentos por vales-presentes
- Registro e processamento de ordens de cliente no PDV
- Lançamento de documentos fiscais em demonstrativos de varejo no Commerce headquarters
- Vendas via lojas de comércio eletrônico
- Vendas do call center

### <a name="fiscal-registration-for-brazil"></a>Registro fiscal do Brasil

O registro fiscal é o registro imediato de vendas de varejo por leis fiscais locais que têm como objetivo impedir a fraude fiscal no setor varejista. Os seguintes métodos de registro fiscal principal estão disponíveis no Brasil:

- Geração de um documento fiscal eletrônico NFC-e para uma venda de varejo e envio do documento para autoridades fiscais (SEFAZ \[Secretaria de Fazenda\]) por meio de um serviço Web dedicado mantido pela SEFAZ.
- Registro de uma venda de varejo, em um dispositivo fiscal SAT conectado ao PDV, usando um documento fiscal eletrônico CF-e.
- Registro de uma venda de varejo em uma impressora fiscal conectada ao PDV.

O Commerce oferece suporte ao registro fiscal por meio da [Estrutura de integração fiscal](../localizations/fiscal-integration-for-retail-channel.md) e de suas extensões para países ou regiões específicas. A funcionalidade de [Relatório Eletrônico](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md) é usada para configurar formatos de documentos fiscais eletrônicos que atendam aos requisitos legais no Brasil.

> [!NOTE]
> A integração com impressoras fiscais não está disponível no Commerce. Você pode aproveitar os [recursos de N-1](../dev-itpro/n-1-installation-configuration.md) para integrar o Retail EPOS (Enterprise Point of Sale) do Microsoft Dynamics AX 2012 R3, que oferece suporte à integração com impressoras fiscais para o Brasil no Commerce headquarters.

## <a name="availability-of-commerce-localization-features-for-brazil"></a>Disponibilidade dos recursos de localização do Commerce para o Brasil

| Recurso                                                                  | Disponibilidade geral (GA) | Lançamento-Disponibilidade Geral | Não planejado |
|--------------------------------------------------------------------------|---------------------------|---------|-------------|
| Gerenciamento de produtos de varejo e cálculo e configuração de imposto                 | X                         |         |             |
| NFC-e (modelo 65) e DANFE para vendas de varejo                              | X                         |         |             |
| Comunicação com a SEFAZ                                                 | X                         |         |             |
| Demonstrativos de varejo no Commerce Headquarters                               | X                         |         |             |
| Tratamento de informações do cliente fiscal (por exemplo, CPF/CNPJ)          | X                         |         |             |
| NF-e (modelo 55) e DANFE para devoluções de vendas                              | X                         |         |             |
| A contingência de NFC-e/NF-e no PDV (modo offline)                         | X                         |         |             |
| Transmissão de NFC-e/NF-e em contingência do Commerce headquarters     | X                         |         |             |
| Cancelamento de NFC-e                                                       | X                         |         |             |
| Cancelamento de NFC-e por substituição, descarte                              |                           | X       |             |
| Integração de TEF (Adyen e recursos básicos)                           |                           | X       |             |
| CF-e (modelo 59) para vendas em São Paulo e integração com um dispositivo SAT |                           | X       |             |
| Busca de clientes por números de registro no PDV               |                           | X       |             |
| Integração de TEF (recursos avançados e provedores adicionais)         |                           | X       |             |
| Documentos fiscais para ordens de cliente do PDV                        |                           | X       |             |
| NF-e vinculada a NFC-e/CF-e e DANFE                                      |                           | X       |             |
| Suporte de N-1 para atualização do AX 2012 R3                                  |                           | X       |             |
| Recursos de comércio eletrônico para o Brasil                                       |                           | X       |             |
| Mesclagem de CNPJ/CPF nos registros principais do cliente no call center           |                           | X       |             |
| Documentos fiscais de varejo em demonstrativos do livro fiscal\*                      |                           |         | X           |
| Integração de PDV com impressoras fiscais                              |                           |         | X           |

\* *Demonstrativos do livro fiscal* são demonstrativos de remuneração e restituição do SPED (Sistema Público de Escrituração Digital) Fiscal, de Contribuições de SPED e ICMS-ST (Imposto sobre Circulação de Mercadorias e Serviços - Substituição Tributária) para os estados suportados.

## <a name="commerce-functionality-for-brazil"></a>Funcionalidade de comércio para o Brasil

A funcionalidade de comércio para o Brasil consiste nas seguintes partes:

- Os recursos de POS comuns disponíveis aos clientes em todos os países ou regiões.
- Recursos específicos ao Brasil, como a comunicação com a SEFAZ

### <a name="common-pos-features"></a>Recursos de POS comuns

Para saber mais sobre os recursos de POS disponíveis para os clientes em todos os países ou regiões, consulte a [página inicial do Commerce](../index.md).

### <a name="brazil-specific-pos-features"></a>Recursos de POS específicos ao Brasil

Os seguintes recursos de POS específicos ao Brasil são habilitados após a localização do Commerce para o Brasil ser configurada e implantada:

- Documento fiscal eletrônico para consumidores no Brasil (NFC-e)
- Gerenciamento de informações do cliente no Brasil
- Cancelamento e devolução de NFC-e
- Registro adiado da NFC-e emitida no moto de contingência
- Postagem e controle de documentos fiscais eletrônicos

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
