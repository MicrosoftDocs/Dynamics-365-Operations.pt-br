---
title: Introdução ao Faturamento eletrônico para o Egito
description: Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para o Egito no Finance e no Supply Chain Management.
author: gionoder
ms.date: 04/20/2021
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
ms.openlocfilehash: 133c47d52bb301f862888c367d19fd58701ecb3c
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6340120"
---
# <a name="get-started-with-electronic-invoicing-for-egypt"></a>Introdução ao Faturamento eletrônico para o Egito

[!include [banner](../includes/banner.md)]

Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para o Egito. O tópico guia você pelas etapas de configuração que dependem do país para o Regulatory Configuration Services (RCS) e complementam as etapas descritas em [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuração específica de país para o recurso Fatura eletrônica do Egito (EG)

Alguns dos parâmetros do **recurso Fatura eletrônica do Egito (EG)** são publicados com valores padrão. Revise os valores e, se necessário, atualize-os para refletir melhor sua operação de negócios antes de implantar o recurso Faturamento eletrônico no ambiente de serviço.

Esta seção complementa a seção **recurso Configuração específica do país para Faturamento eletrônico** no tópico [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

### <a name="prerequisites"></a>Pré-requisitos

Antes de concluir o procedimento nesta seção, você deverá:

- Crie um segredo de certificado digital, conforme descrito na seção **Criar segredo de certificado digital** em [Introdução com a administração do serviço de Faturamento eletrônico](e-invoicing-get-started-service-administration.md). Para fins de teste, a autoridade de impostos egípcia fornece certificados digitais de teste específicos que devem ser usados somente durante fases de validação de solução e teste. Para obter mais informações, consulte o site da autoridade fiscal egípcia usando o link fornecido no [SDK de faturamento eletrônico egípcio](https://sdk.sit.invoicing.eta.gov.eg/faq/).

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Faturamento eletrônico**.
2. Na página **Recursos do Faturamento eletrônico**, verifique se o recurso **Fatura eletrônica egípcia (EG)** que você criou foi selecionado.
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
4. Na guia **Configurações**, na grade, selecione a configuração do recurso **Fatura de venda**.
5. Selecione **Editar** e, na guia **Ações** do grupo de campos **Ações**, selecione **Assinar documento json para autoridade fiscal egípcia**.
6. No grupo de campos **Parâmetros**, selecione o parâmetro, **Nome do certificado** e selecione o nome do certificado digital criado para ser usado com o recurso Faturamento eletrônico.
7. No grupo de campos **Ações**, selecione **Integrar com o serviço ETA egípcio**. Repita essa etapa para as duas ocorrências dessa ação.
8. No grupo de campos **Parâmetros**, selecione **URL do serviço Web** e **URL do serviço de logon** e, se necessário, analise os parâmetros da URL. Consulte o site da autoridade fiscal egípcia para obter a URL de Testes e Produção usando o link fornecido no [SDK de faturamento eletrônico egípcio](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Selecione **Salvar** e feche a página.
10. Para implantar o recurso Faturamento eletrônico no ambiente de serviço, consulte [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuração específica do país da configuração do aplicativo para o recurso Fatura eletrônica egípcia (EG)

Conclua estas etapas antes de implantar a configuração do aplicativo no aplicativo Finance ou Supply Chain Management conectado.

Esta seção complementa a seção **Configuração específica do país da configuração do aplicativo** no tópico [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Faturamento eletrônico**.
2. Na página **Recursos do Faturamento eletrônico**, verifique se o recurso **Fatura eletrônica egípcia (EG)** está selecionado.
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
4. Na guia **Configurações**, selecione **Configuração do aplicativo** e, no campo **Aplicativo conectado**, selecione o aplicativo onde deseja implantar.
5. No campo **Nome da tabela**, verifique se o diário de fatura do cliente está selecionado.
6. Selecione **Tipos de resposta** e selecione **Novo**.
7. No campo **Tipo de resposta**, insira "Resposta" e, no campo **Descrição**, insira "Descrição".
8. No campo **Status de envio**, selecione **Pendente**.
9. No campo **Mapeamento de modelos**, selecione **Mapeamento de modelos de mensagem de resposta**, com **(Versão preliminar) Formato de importação de mensagem de resposta** e, em seguida, selecione **Salvar**.
10. Selecione **Novo** e, no campo **Tipo de resposta**, insira "ResponseData" como um valor fixo. No campo **Descrição**, insira "Descrição".
11. No campo **Status de envio**, selecione **Pendente**.
12. No campo **Nome da entidade de dados**, selecione **Cabeçalhos da fatura de venda V2**.
13. No campo **Mapeamento de modelos**, selecione **Importação de dados de resposta egípcia**, com **(Versão preliminar) Importação de dados de resposta egípcia** e, em seguida, selecione **Salvar**.
14. Para implantar a configuração do aplicativo no aplicativo Finance ou Supply Chain Management conectado, consulte [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Aviso de privacidade

A habilitação do recurso **Fatura eletrônica egípcia (EG)** pode exigir o envio de dados limitados, incluindo a ID de registro de imposto da organização. Esses dados serão transmitidos a agências de terceiros autorizadas pela autoridade fiscal com a finalidade de enviar faturas eletrônicas a essa autoridade fiscal no formato predefinido exigido para integração com o serviço Web do governo. Um administrador pode habilitar e desabilitar o recurso navegando até **Administração da organização** > **Configuração** > **Parâmetros de documento eletrônico**. Na guia **Recursos**, selecione a linha que contém o recurso **Fatura eletrônica egípcia (EG)** e, em seguida, faça a seleção apropriada. Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte as seções de aviso de privacidade da documentação de recursos específicos do país para obter mais informações.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md)
- [Faturas eletrônicas do cliente no Egito](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
