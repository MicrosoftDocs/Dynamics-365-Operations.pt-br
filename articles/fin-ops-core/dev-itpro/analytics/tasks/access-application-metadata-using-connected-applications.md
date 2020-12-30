---
title: Acessar metadados do aplicativo usando aplicativos conectados
description: As etapas deste tópico explicam como um usuário do Regulatory Configuration Service (RCS) pode criar um novo mapeamento de modelo de relatório eletrônico (ER) por meio de metadados no Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 751ac21dc056373e1cd89a5149bf38789134e0cc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682132"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Acessar metadados do aplicativo usando aplicativos conectados

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário do Regulatory Configuration Service (RCS) na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um novo mapeamento de modelo de relatório eletrônico (ER) por meio de metadados do Finance and Operations. Os metadados do aplicativo serão acessados online usando o aplicativo conectado de RCS. O mapeamento de modelo ER de exemplo será configurado para acessar transações de comércio exterior. Para concluir estas etapas, no RCS, primeiro conclua as etapas do tópico [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). Se você não concluiu as etapas do tópico [Acessar metadados do aplicativo usando a configuração ER](access-application-metadata-er-configuration.md), vá para a [página Exemplos de relatórios eletrônicos](https://go.microsoft.com/fwlink/?linkid=862266) para baixar e salvar as seguintes configurações de ER: Metadados de comércio exterior.xml; Modelo de comércio exterior.xml; Mapeamento de comércio exterior.xml e conclua as etapas no procedimento.

## <a name="prerequisites"></a>Pré-requisitos
1. Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**. 
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="get-required-er-configurations"></a>Obtenha configurações de ER necessárias
1. Clique em **Configurações de relatórios**. 
2. Se você já tiver concluído as etapas no procedimento [Acessar metadados do aplicativo usando a configuração ER](access-application-metadata-er-configuration.md), já terá todas as configurações ER necessárias (metadados de comércio exterior, configurações de modelo e mapeamento) na instância do RCS atual. Você pode ignorar todas as etapas restantes desta subtarefa. 
3. Clique em **Taxa de câmbio**. 
4. Clique em **Carregar de um arquivo XML**. 
5. Clique em **Procurar** e selecione o arquivo **Metadados de comércio exterior.xml**. 
6. Clique em **OK**. 
7. Clique em **Taxa de câmbio**. 
8. Clique em **Carregar de um arquivo XML**. 
9. Clique em **Procurar** e selecione o arquivo **Modelo de comércio exterior.xml**. 
10. Clique em **OK**. 
11. Clique em **Taxa de câmbio**. 
12. Clique em **Carregar de um arquivo XML**. 
13. Clique em **Procurar** e selecione o arquivo **Mapeamento de comércio exterior.xml**. 
14. Clique em **OK**. 

## <a name="register-a-connected-application"></a>Registre um aplicativo conectado
1. Feche a página. 
2. Feche a página. 
3. Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**. 
4. Clique em **Aplicativos conectados**. 
5. Verifique se o aplicativo configurado é baseado em Azure e está disponível para o usuário do RCS atual. Também é necessário que o usuário do RCS atual tenha acesso ao aplicativo selecionado e esteja registrado como um usuário desse aplicativo com uma função que lhes concede privilégios para acessar metadados do aplicativo. 
6. Clique em **Novo**. 
7. No campo **Nome**, digite 'MyConnectedApp'. 
8. No campo **Aplicativo**, digite 'https:// mycompany.operations.dynamics.com'. 
9. No campo **Locatário**, digite "mycompany.onmicrosoft.com". 
10. Clique em **Salvar**. 
11. Quando você verificar a conexão com o aplicativo, na página **Conectar-se ao aplicativo remoto**, clique no link **Clique aqui para conectar-se ao aplicativo remoto selecionado**. 
12. Clique em **Verifique a conexão**. 
13. Clique em **Fechar**. 
14. Quando a validação da conexão for bem-sucedida, os detalhes da versão e do locatário serão atualizados para o aplicativo configurado na grade atual. 

## <a name="review-existing-model-mapping-configuration"></a>Reveja a configuração de mapeamento do modelo existente
1. Feche a página. 
2. Clique em **Configurações de relatórios**. 
3. Na árvore, expanda **Modelo de comércio exterior**. 
4. Na árvore, selecione **Modelo de comércio exterior\Mapeamento de comércio exterior**. 
5. Expanda a seção **Pré-requisitos**. 

    > [!NOTE]
    > Atualmente, o mapeamento se refere à configuração dos metadados. Os metadados de aplicativos dessa configuração serão oferecidos durante a criação desse mapeamento de modelo. 

6. Clique em **Designer**. 
7. Clique em **Designer**. 
8. Na árvore, selecione **Dynamics 365 for Operations\Registros da tabela**. 
9. Clique em **Adicionar raiz**. 
10. No campo **Tabela**, insira ou selecione um valor. 

    > [!NOTE]
    > Atualmente, o mapeamento se refere à configuração dos metadados. Os metadados de aplicativos dessa configuração serão oferecidos durante a criação desse mapeamento de modelo. 

11. Clique em **Cancelar**. 
12. Feche a página. 
13. Feche a página. 

## <a name="assign-connected-application-to-model-mapping"></a>Atribua um aplicativo conectado ao mapeamento de modelo 
1. Clique em **Editar**. 
2. Selecione o aplicativo **MyConnectedApp**. 

    > [!NOTE]
    > Atualmente, este mapeamento refere-se aos metadados do aplicativo conectado selecionado. Quando o mesmo mapeamento referir-se à configuração de metadados e ao aplicativo associado simultaneamente, os metadados do aplicativo conectado serão usados. 

3. Clique em **Designer**. 
4. Clique em **Designer**. 
5. Na árvore, selecione **Dynamics 365 for Operations\Registros da tabela**. 
6. Clique em **Adicionar raiz**. 
7. No campo **Tabela**, insira ou selecione um valor. 

    > [!NOTE]
    > Mais de duas tabelas do aplicativo foram oferecidas agora pois esse mapeamento utiliza todos os metadados do aplicativo conectado que foram atribuídos a ele. 

8. Clique em **Cancelar**. 
9. Clique em **Validar**. 

    > [!NOTE]
    > Associamos com êxito elementos de modelo de dados com itens de fontes de dados que serão descritos usando detalhes de metadados do aplicativo conectado que foram atribuídos a este mapeamento. 

10. Feche a página. 
11. Feche a página. 

Quando você precisar avaliar esse mapeamento de modelo usando metadados de um aplicativo de versão diferente, registre outro aplicativo conectado, atribua-o a este mapeamento de modelo e valide-o em relação aos novos metadados.
