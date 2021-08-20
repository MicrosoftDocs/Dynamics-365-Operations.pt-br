---
title: Visão geral do Faturamento eletrônico
description: Este tópico fornece informações sobre o Faturamento eletrônico no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
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
ms.openlocfilehash: eebe51ae89326965235c031ed11008c6af3d453f0f297d3201862946ab4caca9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741499"
---
# <a name="electronic-invoicing-overview"></a>Visão geral do Faturamento eletrônico

[!include [banner](../includes/banner.md)]

O Faturamento eletrônico para o Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management é um serviço multilocatário hiperescalável que permite o processamento configurável de documentos de fatura eletrônica e troca configurável de documentos. As regras de processamento e integração são totalmente configuráveis e a lógica é executada fora do Finance e do Supply Chain Management. O serviço é direcionado principalmente para o processamento de fatura eletrônica em cenários de empresa para governo, mas pode ser configurado de forma personalizada para outros fins.

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

Para usar o Faturamento eletrônico, você deve instalá-lo a partir do seu projeto no Microsoft Dynamics Lifecycle Services (LCS). Em seguida, siga o procedimento de configuração para ativar a integração com o Finance ou o Supply Chain Management. Para obter mais informações, consulte [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="service-availability"></a><a name="availability"></a>Disponibilidade do serviço

No momento, o Faturamento eletrônico está disponível para clientes por meio do programa de visualização e, na próxima fase, o serviço estará geralmente disponível. Como a funcionalidade que trata de requisitos específicos de país/região pode ser limitada a diferentes fases do lançamento, você sempre deve verificar a documentação mais atualizada que destaca a cobertura e o escopo das soluções específicas de país/região com suporte.

O Faturamento eletrônico é implantado nas seguintes regiões do Azure:

- Estados Unidos
- Europa

> [!NOTE]
> O Faturamento eletrônico não dá suporte a implantações locais.

## <a name="extended-configurability"></a>Configurabilidade estendida

O Faturamento eletrônico pode ser usado em cenários em que você deve criar e enviar um documento eletrônico para os participantes designados. Ele foi especificamente projetado para executar um fluxo configurável de ações de processamento, com base nos dados recebidos. As opções de capacidade de configuração disponíveis no Finance e no Supply Chain Management se limitam à transformação do documento. O serviço estende essas opções adicionando as integrações configuráveis que estão disponíveis nele. Além disso, todas as funcionalidades de faturas eletrônicas disponibilizadas anteriormente, como NF-e (nota fiscal eletrônica brasileira), comprovante fiscal mexicano por Internet (CFDI) ou outras funcionalidades do UBL/PEPPOL do Leste Europeu (Universal Business Language/Pan-European Public Procurement OnLine) usarão configurações para exportação e importação e para habilitar integrações com serviços Web externos.

## <a name="feature-highlights"></a>Destaques do recurso

- Integração pronta para uso com o Finance e o Supply Chain management
- Experiência de usuário consistente para a configuração e o monitoramento do processo de fatura eletrônica para todos os países ou regiões
- Adoção mais rápida, fácil e barata de soluções de Faturamento eletrônico em novos países ou regiões
- Configuração do serviço por meio da configuração de RCS (Regulatory Configuration Services) e do Recurso de globalização
- Transformação de dados comerciais em vários formatos de fatura eletrônica (XML, Notação de Objeto de JavaScript, \[JSON\], TXT e valores separados por vírgula \[CSV\]) usando configurações definidas no RCS:

    - Formatos eletrônicos de relatório que estão disponíveis para países ou regiões em que a capacidade de configuração para a transformação de fatura eletrônica não está disponível

- Envio configurável de faturas eletrônicas para serviços Web externos, incluindo o tratamento de certificados por meio de assinaturas digitais:

    - Integração interna, fácil de estender e configurável com conteúdo adicional para vários países

    > [!NOTE]
    > No momento, há suporte a um número limitado de envios diretos. Para obter mais informações, consulte a seção [Disponibilidade do serviço](#availability), anteriormente neste tópico. O suporte será estendido no futuro.

- Tratamento de respostas de serviços Web, incluindo tratamento configurável de mensagens de exceção
- Suporte para assinaturas eletrônicas (por exemplo, usando o algoritmo de assinatura XMLDSig)
- Processamento em lotes de mensagens da fatura eletrônica

## <a name="architecture-and-data-flow"></a>Arquitetura e fluxo de dados

Quando o Faturamento eletrônico é instalado do LCS e a configuração necessária é concluída em todos os aplicativos necessários, uma conexão segura é estabelecida. O serviço está localizado no momento em data centers nos Estados Unidos e na Europa. Portanto, o local de serviço pode ser diferente do local da instância do Finance ou do Supply Chain Management relacionada. Depois de concluir a configuração do Faturamento eletrônico e ativar a integração, sempre que uma fatura eletrônica for enviada, os dados mestres e os dados transacionais relacionados a um documento específico serão enviados ao faturamento eletrônico.

> [!NOTE]
> Se a sua fatura eletrônica ou qualquer outro documento contiver dados pessoais, verifique se o uso desse recurso atende ao Regulamento Geral sobre a Proteção de Dados (GDPR) e outras regulamentações relacionadas à transferência de dados pessoais.

### <a name="high-level-description-of-the-data-flow"></a>Descrição de alto nível do fluxo de dados

1. O cliente envia um documento comercial canônico ao serviço.
2. Com base nas informações de contexto recebidas do cliente, o serviço seleciona o fluxo de processamento aplicável.
3. O serviço executa as ações de processamento. Essas ações podem incluir a transformação do documento comercial em uma fatura eletrônica, aplicando uma assinatura eletrônica e enviando o documento a um serviço Web externo.
4. Todos os documentos recebidos e processados são armazenados no armazenamento de Blobs do Azure do cliente.
5. Todos os segredos e certificados de locatário usados para processamento são armazenados no cofre de chaves do Azure do cliente.
6. O serviço fornece informações sob demanda ao cliente sobre o status de processamento do documento comercial enviado.
7. O cliente recebe informações sobre a execução de processamento concluída e disponibiliza todas as informações de log. Ele também disponibiliza o documento que foi criado ou recebido durante o processamento de fluxo.

A ilustração a seguir mostra como os dados fluem de e para o Faturamento eletrônico.

![Fluxo de dados para o Faturamento eletrônico.](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Aviso de privacidade
A habilitação e o uso de faturamento eletrônico podem exigir o envio de dados limitados, que incluem a ID de registro de imposto da organização. Isso será transmitido a agências de terceiros autorizadas pelas autoridades fiscais com a finalidade de enviar faturas eletrônicas nos formatos predefinidos exigidos para a integração com esses serviços Web do governo. Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte as seções de aviso de privacidade da documentação de recursos específicos do país para obter mais informações.

## <a name="additional-resources"></a>Recursos adicionais
- [Administração de serviço](e-invoicing-service-administration.md)
- [Configurar faturas eletrônicas no RCS](e-invoicing-configuration-rcs.md)
- [Emitir faturas eletrônicas no Finance e no Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
