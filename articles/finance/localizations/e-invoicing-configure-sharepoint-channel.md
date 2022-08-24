---
title: Configurar um canal do SharePoint
description: Este artigo explica como configurar um canal de do Microsoft SharePoint para processar faturas eletrônicas recebidas.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 92eaa357c6d72cc637d4ce353702e5d41ecf4338
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272294"
---
# <a name="configure-a-sharepoint-channel"></a>Configurar um canal do SharePoint

[!include [banner](../includes/banner.md)]

Como pré-requisito para configurar um canal do Microsoft SharePoint para processar documentos de entrada, conclua as etapas descritas em [Configurar uma conexão do SharePoint](e-invoicing-create-sharepoint-connection.md).

Em seguida, você poderá usar o canal do SharePoint para importar faturas de fornecedores eletrônicos de arquivos armazenados nas suas pastas do SharePoint.

1. No seu site do SharePoint, crie as seguintes pastas:

    - **Pasta principal** – A pasta da qual o serviço processará os arquivos.
    - **Pasta de arquivamento** – A pasta na qual os arquivos processados serão armazenados.
    - **Pasta de erros** – A pasta para a qual o sistema moverá os arquivos, caso o processamento falhe.

2. Selecione o recurso de faturamento eletrônico que você criou no Regulatory Configuration Service (RCS). Certifique-se de selecionar a versão com o status **Rascunho**.
3. Na guia **Configurações**, selecione **Adicionar**.
4. Na caixa de diálogo **Criar configuração do recurso** na caixa de diálogo suspensa, no grupo de campos **Novo**, selecione a opção **Configuração personalizada**:
5. No grupo de campos **Tipo de configuração**, selecione a opção **Canal de dados**.
6. No campo **Selecionar canal de dados**, selecione **Pasta do SharePoint**.
7. Selecione **Criar**.
8. Selecione a linha que você criou antes e selecione **Editar**.
9. Na guia **Canal de dados**, na seção **Parâmetros**, defina os seguintes campos obrigatórios.

    | Campo                 | Descrição |
    |-----------------------|-------------|
    | Canal de dados          | Digite um nome exclusivo para identificar o canal de dados. O nome pode ter no máximo 10 caracteres. Ele será referenciado nas regras de aplicabilidade e em aplicativos conectados durante o processo de comunicação. |
    | Endereço do SharePoint    | Entre com o URL do SharePoint. Por exemplo, insira `<domain>.sharepoint.com`. |
    | Id do aplicativo        | Digite o nome do segredo do Azure Key Vault que contém a ID da conta de usuário de email do SharePoint. Esse segredo deve ser criado no Key Vault e configurado no seu ambiente de serviço. O valor é o valor do **ID do aplicativo (cliente)** de [Configurar conexão do SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Segredo do aplicativo    | Digite o nome do segredo do Key Vault que contém a senha da conta de usuário de email do SharePoint. O valor é o valor do **Segredo do registro de aplicativo** de [Configurar conexão do SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Nome do site             | Insira o nome do site do SharePoint. |
    | Nome da biblioteca de documentos | Digite o nome da biblioteca de documentos do SharePoint. |
    | Tempo limite               | Digite o tempo máximo, em milissegundos (MS), que o sistema deve esperar por uma resposta. O valor padrão é 10.000 ms (10 segundos). |
    | Pasta principal           | Especifique a fonte de importação de arquivo ou a pasta da qual o serviço deve processar arquivos. |
    | Pasta de arquivo morto        | Especifique a pasta na qual os arquivos processados devem ser armazenados. |
    | Pasta de erros          | Especifique a pasta para a qual o sistema deve mover os arquivos se o processamento falhar. |
    | Tamanho máximo do arquivo         | Insira o tamanho máximo, em bytes, de um único arquivo processado. O valor padrão é 20.000.000 bytes. |
    | Número máximo de arquivos      | Digite a quantidade máxima de arquivos a serem processadas para uma única ação. Caso você não queira limitar o número de arquivos, defina o valor como **0** (zero). |
    | Filtro de arquivo           | Insira uma cadeia de caracteres para filtrar por nome de arquivo. Esse campo é opcional. Há suporte para uma máscara simples, tal como **\*smth\*.ext**, na qual cada asterisco (\*) representa zero ou mais ocorrências de qualquer caractere. Por exemplo, digite **\*.pdf** para configurar o canal para ler arquivos PDF. |
    | Nome do arquivo personalizado      | Digite o nome do arquivo personalizado do cliente. |

10. Na guia **Regras de aplicabilidade**, revise e atualize os critérios, conforme necessário. O valor do campo **Canal** deve ser igual ao valor inserido no campo **Canal de dados** na etapa anterior.
11. Selecione **Salvar** e feche a página.
