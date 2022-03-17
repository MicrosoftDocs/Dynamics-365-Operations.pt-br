---
title: Visão geral do Faturamento eletrônico
description: Este tópico fornece uma visão geral sobre o Faturamento eletrônico no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23a98706bc2ab0abc2c72e9f20d8e8fbff56b2b9
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371445"
---
# <a name="electronic-invoicing-overview"></a>Visão geral do Faturamento eletrônico

[!include [banner](../includes/banner.md)]

O Faturamento eletrônico para o Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management é um serviço multilocatário hiperescalável que permite o processamento configurável de faturas eletrônicas e troca configurável de documentos. As regras de processamento e integração são totalmente configuráveis e a lógica é executada fora do Finance e do Supply Chain Management. O serviço é direcionado principalmente para o processamento de documentos de fatura eletrônica em cenários de empresa para governos. No entanto, ele pode ser configurado de forma personalizada para outros fins, como cenários entre empresas para diferentes tipos de documentos.

O Faturamento eletrônico pode ajudá-lo a atingir as seguintes metas:

- Adoção rápida e fácil de requisitos específicos de país/região
- Implementações padronizadas de uma solução de Faturamento eletrônico
- Rastreamento aprimorado do histórico de documentos
- Ciclo de implementação mais curto
- TCO (custo total de propriedade) reduzido
- Configurações facilmente ajustáveis que não exigem alterações de código
- Pacote de configuração simplificado
- A exportação, a importação e a integração internas e a fácil extensibilidade no processamento de documentos de fatura eletrônica
- Fácil reutilização das mesmas configurações de exportação, importação e integração em empresas

## <a name="service-availability"></a>Disponibilidade do serviço

No momento, o recurso de faturamento eletrônico está disponível para Finance e Supply Chain Management. Para obter mais informações, revise os termos e condições de licença do seu aplicativo.

Como a funcionalidade que trata de requisitos específicos de país/região pode ser limitada a diferentes fases do lançamento, você sempre deve revisar a documentação mais atualizada que destaca a cobertura e o escopo das soluções específicas de país/região com suporte.

O Faturamento eletrônico é implantado nas seguintes regiões do Azure:

- Estados Unidos
- Europa
- Ásia

> [!NOTE]
> O Faturamento eletrônico não dá suporte a implantações locais.

## <a name="feature-highlights"></a>Destaques do recurso

- Integração pronta para uso com o Finance e o Supply Chain Management
- Uma experiência de usuário consistente para a configuração e o monitoramento do processo de fatura eletrônica para todos os países ou regiões
- Adoção mais rápida, fácil e barata de soluções de Faturamento eletrônico em novos países ou regiões
- Configuração do serviço por meio da configuração de RCS (Regulatory Configuration Service) e de Recursos de globalização
- Transformação de dados comerciais em vários formatos de fatura eletrônica (XML, Notação de Objeto de JavaScript, \[JSON\], TXT e valores separados por vírgula \[CSV\]) usando configurações definidas no RCS:

    - Formatos eletrônicos de relatório (ER) que estão disponíveis para países e regiões em que a capacidade de configuração para a transformação de fatura eletrônica não está disponível

- Envio configurável de faturas eletrônicas para serviços Web externos, incluindo o tratamento de certificados por meio de assinaturas digitais:

    - Integração interna, fácil de estender e configurável com conteúdo adicional para vários países e regiões

- Tratamento de respostas de serviços Web, incluindo manuseio configurável de mensagens de exceção
- Suporte para assinaturas eletrônicas (por exemplo, assinaturas eletrônicas que usam o algoritmo de assinatura do XMLDSig)
- A habilidade de enviar documentos para emails e armazená-los no SharePoint
- Processamento em lotes de mensagens de fatura eletrônica
- Transformação configurável de documentos de entrada e processamento desses documentos no Finance e Supply Chain Management
- A capacidade de receber documentos de entrada de canais como email e o SharePoint

## <a name="privacy-notice"></a>Aviso de privacidade

Habilitar o recurso Faturamento eletrônico pode exigir o envio de dados limitados. Esses dados incluem a ID de registro de imposto da organização. Esses dados serão transmitidos a agências de terceiros que são autorizadas pelas autoridades fiscais com a finalidade de enviar faturas eletrônicas nos formatos predefinidos exigidos para a integração com esses serviços Web do governo. Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Para obter mais informações, consulte a seção "Aviso de privacidade" da documentação de recursos específicos do país/região.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
