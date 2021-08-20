---
title: Preparar os metadados do aplicativo a serem usados no RCS
description: Este tópico descreve como criar uma nova configuração de relatório que contenha metadados do aplicativo.
author: NickSelin
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71a33a69796b31c456bfcc5abbb3b18bcb1064be65c1c58b36656a9cebfbf47d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750565"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Preparar os metadados do aplicativo a serem usados no RCS
[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório eletrônico (ER) contendo metadados do aplicativo para criar configurações de mapeamentos do modelo ER no Regulatory Configuration Service (RCS). Essa configuração será usada para criar uma configuração de mapeamento do modelo ER de exemplo para acessar transações de comércio exterior. Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa. Para concluir estas etapas, primeiro conclua as etapas do tópico, [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="prerequisites"></a>Pré-requisitos
1.    Acesse **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**. 
2.    Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). 
3.    Clique em **Configurações de metadados**. 
4.    Suponha que o RCS seja usado para criar uma solução de ER para um aplicativo do Finance and Operations que gere documentos eletrônicos contendo informações do domínio de negócios de comércio exterior. Para especificar o mapeamento entre o modelo de dados do ER e fontes de dados necessários, no RCS precisamos ter acesso a metadados do aplicativo Finance and Operations. Portanto, como parte da criação da solução de ER, definimos uma nova configuração de metadados de ER contendo todos os metadados atualmente necessários para a geração de relatórios de ER para o domínio comercial selecionado. 

## <a name="add-metadata-configuration"></a>Adicione a configuração de metadados 
1.    Clique em **Criar configuração** para abrir a caixa de diálogo suspensa. 
2.    No campo **Nome**, digite 'Metadados de comércio exterior'. 
3.    Clique em **Criar configuração**. 
4.    Clique em **Designer**. 
5.    Clique em **Adicionar**. 
  
> [!NOTE]
> Você pode selecionar todos os metadados do aplicativo inteiro, modelos selecionados ou módulos selecionados. Lembre-se de que, nesse caso, os seguintes metadados serão adicionados automaticamente: tabelas de registros, enumerações e tipos de dados estendidos. Quando tipos adicionais de metadados são necessários, eles devem ser adicionados manualmente. 
 
Temos algumas transações de comércio exterior com metadados relacionados, em que itens de metadados foram selecionados manualmente. 
  
6.    Clique em **Adicionar fonte de dados**. 
7.    Clique em **Registros de tabela**. 
8.    Use o Filtro Rápido para filtrar no campo **Nome** com um valor de 'Intrastat'. 
9.    Selecione o registro de tabela **Intrastat**. 
10.    Clique em **OK**.
  
Adicionamos informações de metadados sobre a tabela de registros Intrastat. 
  
11.    Na árvore, expanda **Registros de tabela Intrastat**\>**Relações**. 
12.    Na árvore, selecione **Registros de tabela Intrastat**\>**Relações\IntrastatCommodity (Registros de tabela EcoResCategory)**.     
13.    Clique em **Adicionar metadados**. 
  
> [!NOTE]
> Os metadados sobre relações necessárias para a tabela selecionada de registros devem ser adicionados manualmente. 
  
16.    Clique em **Adicionar fonte de dados**. 
17.    Clique em **Enumeração**. 
18.    Use o Filtro Rápido para filtrar no campo **Nome** com um valor de 'IntrastatDirection'. 
19.    Selecione o registro **Enumeração IntrastatDirection**. 
20.    Clique em **OK**. 
21.    Clique em **Salvar**.  
22.    Feche a página. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>Preencha a versão de rascunho de configuração de metadados
1.    Clique em **Alterar status**. 
2.    Clique em **Concluir**. 
3.    Clique em **OK**. 
4.    Selecione a versão concluída **1**. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>Exporte a versão concluída da configuração de metadados do aplicativo como o arquivo XML
1.    Clique em **Taxa de câmbio**. 
2.    Clique em **Exportar como o arquivo XML**. 
3.    Clique em **OK**. 
    
A configuração de metadados de ER criada foi salva como um arquivo XML que pode ser importado para o RCS e usado como a fonte de informações sobre metadados para o domínio comercial de comércio exterior. Com base nessas informações, podemos especificar o mapeamento entre metadados de aplicativos e o modelo de dados do ER.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]