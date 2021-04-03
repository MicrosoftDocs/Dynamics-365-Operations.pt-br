---
title: Introdução ao complemento de faturamento eletrônico para o Brasil
description: Este tópico fornece informações que ajudarão você a começar a usar o complemento Faturamento eletrônico para o Brasil no Finance e Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: eaf9433ad2d9ccf3d3c5632d0f2d4fe772ff8bde
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592661"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Introdução ao complemento de faturamento eletrônico para o Brasil 

[!include [banner](../includes/banner.md)]

Este tópico explica como começar a usar o complemento de faturamento eletrônico para o Brasil. Os procedimentos deste tópico orientam você pelas etapas de configuração que dependem do país para o Regulatory Configuration Services (RCS) e complemente as etapas descritas no tópico [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuração específica de país para o recurso Faturamento eletrônico de NF-e brasileira (BR)

A configuração do recurso Faturamento eletrônico de NF-e brasileira (BR) requer a conclusão de etapas específicas. Alguns dos parâmetros das configurações são publicados com valores padrão, portanto, eles devem ser revisados e atualizados para atender melhor à operação comercial.

### <a name="prerequisites"></a>Pré-requisitos

Antes de concluir o procedimento desta seção, crie um recurso Faturamento eletrônico de NF-e brasileira (BR) para sua organização, conforme descrito na seção **Criar um recurso Faturamento eletrônico no seu provedor da organização** no tópico [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Complemento Faturamento eletrônico**.
2. Na página **Recursos do complemento Faturamento eletrônico**, verifique se o recurso Faturamento eletrônico de **NF-e brasileira** que você criou foi selecionado.
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
4. Na guia **Configurações**, na grade, selecione **Enviar** e selecione **Editar.**
5. Na guia **Ações**, no grupo de campos **Ações**, selecione a ação **(Versão preliminar) Assinar documento XML**.
6. No grupo de campos **Parâmetros**, selecione **Nome do certificado** e, no campo **Valor**, insira o nome do certificado associado ao parâmetro do seu Cofre de chaves.
7. Na guia **Ações**, no grupo de campos **Ações**, selecione a ação **(Versão preliminar) Chamar serviço SEFAZ brasileiro**.
8. No grupo de campos **Parâmetros**, selecione o parâmetro **Endereço da URL**.
9. No campo **Valor**, se necessário, analise e atualize a URL dos serviços Web publicados pela documentação da SEFAZ para seu estado e selecione **Salvar.**
10. Na guia **Regras de aplicabilidade**, no grupo de campos **Configuração de regra de aplicabilidade**, analise e atualize os critérios do campo **Estado**, conforme necessário, para o mesmo estado, ao qual a URL dos serviços Web refere-se.
11. Selecione **Salvar** e feche a página.
12. Para configurar a configuração do aplicativo, consulte [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuração específica do país da configuração do aplicativo para o recurso Faturamento eletrônico de NF-e brasileira (BR)

A definição da Configuração do aplicativo para o recurso Faturamento eletrônico de NF-e brasileira (BR) requer a conclusão de etapas específicas. Conclua estas etapas antes de implantar o recurso Faturamento eletrônico no ambiente de serviço do complemento Faturamento eletrônico.

### <a name="prerequisites"></a>Pré-requisitos

Antes de concluir o procedimento desta seção, crie e inicie a configuração do aplicativo do recurso Faturamento eletrônico de NF-e brasileira (BR) para sua organização, conforme descrito na seção **Criar um recurso Faturamento eletrônico no seu provedor da organização** no tópico [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Complemento Faturamento eletrônico**.
2. Na página **Recursos do complemento Faturamento eletrônico**, verifique se o recurso Faturamento eletrônico de **NF-e brasileira** foi selecionado.
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
4. Na guia **Configurações**, selecione **Configuração do aplicativo** e, no campo **Aplicativo conectado**, selecione o aplicativo para onde deseja implantar.
5. No campo **Nome da tabela**, verifique se **Cabeçalho do documento fiscal** está selecionado.
6. Selecione **Tipos de resposta** e selecione **Novo**.
7. No campo **Tipo de resposta**, insira "Resposta" como um valor fixo e, no campo **Descrição**, insira "Descrição".
8. No campo **Status de envio**, selecione **Pendente**.
9. No campo **Mapeamento de modelos**, selecione **Mapeamento de modelos de mensagem de resposta**, com **(Versão preliminar) Formato de importação de mensagem de resposta** e, em seguida, selecione **Salvar**.
10. Selecione **Novo** e, no campo **Tipo de resposta**, insira "ResponseData" como um valor fixo e, no campo **Descrição**, insira "Descrição".
11. No campo **Status de envio**, selecione **Pendente**.
12. No campo **Mapeamento de modelos**, selecione **Importação de dados de resposta**, com **(Versão preliminar) Formato de importação de dados de resposta de NF-e (BR)** e, em seguida, selecione **Salvar**.
13. Para implantar o recurso Faturamento eletrônico, consulte [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuração específica de país para o recurso Faturamento eletrônico de NFS-e ABRASF Curitiba brasileira (BR)

A configuração do recurso Faturamento eletrônico de NFS-e ABRASF Curitiba brasileira (BR) requer a conclusão de etapas específicas. Alguns dos parâmetros das configurações são publicados com valores padrão, portanto, eles devem ser revisados e atualizados para atender melhor à operação comercial.

### <a name="prerequisites"></a>Pré-requisitos

Antes de concluir o procedimento desta seção, crie um recurso Faturamento eletrônico de NFS-e ABRASF Curitiba brasileira (BR) em sua organização. Isso é descrito na seção **Configurar recurso Faturamento eletrônico** no tópico [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Complemento Faturamento eletrônico**.
2. Na página **Recursos do complemento Faturamento eletrônico**, verifique se o recurso Faturamento eletrônico de **NFS-e ABRASF Curitiba brasileira (BR)** que você criou foi selecionado.
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada e, na guia **Configurações**, na grade, selecione **Enviar**.
4. Selecione **Editar** e, na guia **Ações** do grupo de campos **Ações**, selecione a primeira ocorrência de **(Versão preliminar) Assinar documento xml**.
5. No grupo de campos **Parâmetros**, selecione **Nome do certificado**.
6. No campo **Valor**, insira o nome do certificado associado ao parâmetro do cofre de chaves.
7. No grupo de campos **Ações**, selecione a segunda ocorrência de **(Versão preliminar) Assinar documento xml**.
8. No grupo de campos **Parâmetros**, selecione **Nome do certificado**.
9. No campo **Valor**, insira o nome do certificado associado ao parâmetro do cofre de chaves.
10. Na guia **Ações**, no grupo de campos **Ações**, selecione a ação **(Versão preliminar) Chamar serviço SEFAZ brasileiro**.
11. No grupo de campos **Parâmetros**, selecione o parâmetro **Endereço da URL**.
12. No campo **Valor**, se necessário, analise e atualize a URL dos serviços Web publicados pelo Secretaria da Fazenda da cidade de Curitiba e selecione **Salvar.**
13. Na guia **Configurações**, na grade, selecione **Consultar** e selecione **Editar.**
14. Na guia **Ações**, no grupo de campos **Ações**, selecione a ação **(Versão preliminar) Chamar serviço SEFAZ brasileiro**.
15. No grupo de campos **Parâmetros**, selecione o parâmetro **Endereço da URL**.
16. No campo **Valor**, se necessário, analise e atualize a URL dos serviços Web publicados pelo Secretaria da Fazenda da cidade de Curitiba.
17. Selecione **Salvar** e feche a página.
18. Para configurar a configuração do aplicativo, consulte [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuração específica do país da configuração do aplicativo para o recurso Faturamento eletrônico de NFS-e ABRASF Curitiba brasileira (BR)

A configuração da configuração do aplicativo para o recurso Faturamento eletrônico da NFS-e ABRASF Curitiba brasileira (BR) requer que etapas específicas sejam concluídas antes da implantação do recurso de faturamento eletrônico no ambiente de serviço complementar do faturamento eletrônico.

### <a name="prerequisites"></a>Pré-requisitos

Antes de concluir o procedimento desta seção, crie e inicie um recurso Faturamento eletrônico de NFS-e ABRASF Curitiba brasileira (BR) para sua organização, conforme descrito na seção **Criar um recurso Faturamento eletrônico no seu provedor da organização** no tópico [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md).

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Complemento Faturamento eletrônico**.
2. Na página **Recursos do complemento Faturamento eletrônico**, verifique se o recurso Faturamento eletrônico de **NFS-e ABRASF Curitiba brasileira (BR)** foi selecionado.
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada e, na guia **Configurações**, selecione **Configuração do aplicativo**.
4. No campo **Aplicativo conectado**, selecione o aplicativo onde deseja implantar.
5. No campo **Nome da tabela**, verifique se cabeçalho do documento fiscal está selecionado.
6. Selecione **Tipos de resposta** e selecione **Novo**.
7. No campo **Tipo de resposta**, insira "ABRASFCuritibaSubmitResponse" como um valor fixo e, no campo **Descrição**, insira "Descrição".
8. No campo **Status de envio**, selecione **Pendente**.
9. No campo **Mapeamento de modelos**, selecione **Importação de dados de mensagem**, com **(Versão preliminar) Importação de mensagem de resposta de NFS-e ABRASF Curitiba (BR)** e, em seguida, selecione **Salvar**.
10. Selecione **Novo** e, no campo **Tipo de resposta**, insira "ABRASFCuritibaSubmitResponseData" e, no campo **Descrição**, insira "Descrição".
11. No campo **Status de envio**, selecione **Pendente**.
12. No campo **Mapeamento de modelos**, selecione **Importação de dados de resposta**, com **(Versão preliminar) Formato de importação de dados de resposta de NFS-e ABRASF (BR)** e, em seguida, selecione **Salvar**.
13. Selecione **Novo** e, no campo **Tipo de resposta**, insira "ABRASFCuritibaInquireResponse" como um valor fixo e, no campo **Descrição**, insira "Descrição".
14. No campo **Status de envio**, selecione **Pendente**.
15. No campo **Mapeamento de modelos**, selecione **Importação de dados de mensagem**, com **(Versão preliminar) Importação de mensagem de resposta de NFS-e ABRASF Curitiba (BR).**
16. Selecione **Salvar** e então volte para o tópico [Introdução ao complemento Faturamento eletrônico](e-invoicing-get-started.md) para implantar o recurso Faturamento eletrônico.

## <a name="privacy-notice"></a>Aviso de privacidade
A habilitação da **NF-e Federal - Fatura eletrônica brasileira (BR)** e os recursos **NFS-e - Fatura eletrônica de serviço brasileiro (cidade)** talvez exijam o envio de dados limitados, incluindo a ID de registro de imposto da organização. Os dados são transmitidos a agências de terceiros autorizadas pela autoridade fiscal com a finalidade de enviar faturas eletrônicas a essa autoridade fiscal no formato predefinido exigido para integração com o serviço Web do governo. Como administrador, você pode habilitar ou desativar a **NF-e Federal - Fatura eletrônica brasileira (BR)** e os recursos **NFS-e - Fatura eletrônica de serviço brasileira (cidade)**. As etapas a seguir mostram como fazer isso: 

1. Acesse **Administração da organização** > **Configuração** > **Parâmetros de documentos eletrônicos**. 
2. Na guia **Recursos**, selecione a linha que contém o recurso **NF-e Federal - Fatura eletrônica brasileira (BR)** ou a **NFS-e - Fatura eletrônica de serviço brasileira (serviço)** e selecione o recurso. Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte as seções de aviso de privacidade da documentação de recursos específicos do país para obter mais informações.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do complemento do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao complemento do faturamento eletrônico](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
