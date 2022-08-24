---
title: Conclua, publique e implante um recurso de Globalização
description: Este artigo fornece informações sobre os recursos de ciclo de vida de globalização.
author: gionoder
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 11378991a24e1a5f5e213d64f0f414db2e5c2573
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279890"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Conclua, publique e implante um recurso de Globalização

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Versões de recursos do faturamento eletrônico

Os recursos do faturamento eletrônico têm versões. Quando uma nova versão é criada, o número da versão é incrementado automaticamente.

As versões do recurso de faturamento eletrônico seguem um ciclo de vida que tem até três status:

- **Rascunho** – Quando uma versão do recurso estiver neste status, você poderá editar seus atributos de configuração e seus artefatos (por exemplo, configurações de formato de arquivo).
- **Concluir** – Esse status indica que você concluiu a edição da versão do recurso e não pretende fazer mais atualizações nela. Quando a versão de um recurso tem este status, não é mais possível editá-la nem qualquer um de seus componentes.
- **Publicado** – Este status indica que a versão foi publicada no repositório global associado à sua organização. Quando a versão de um recurso tem este status, não é mais possível editá-la nem qualquer um de seus componentes.

Você pode especificar uma data de **Vigente a partir** para uma nova versão de um recurso de faturamento eletrônico. Dessa forma, você pode definir uma versão padrão que pode ser usada ou que pode ser sobrescrita quando o recurso é implantado no ambiente de serviço.

Para alterar o status de uma versão do recurso de faturamento eletrônico, siga estas etapas.

1. Entre na conta RCS (serviço de configuração regulatória).
2. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. No lado esquerdo da página **Recursos de Faturamento eletrônico**, selecione o recurso de faturamento eletrônico.
4. Na guia **Versões**, no lado direito da página, selecione a versão.
5. Selecione **Alterar status** e selecione **Concluído** (se o status atual for **Rascunho**) ou **Publicado** (se o status atual for **Concluído**).
6. Na caixa de mensagem, selecione **Sim** para confirmar a solicitação.

A alteração manual do status **Concluído** para o status **Publicado** é opcional. As versões do recurso de faturamento eletrônico são atualizadas automaticamente para o status **Publicado** quando são implantadas no ambiente de serviço.

Você pode acompanhar o status na coluna **Status da versão do recurso** na guia **Versões**.

## <a name="deploy-feature-versions"></a>Implantar versões do recurso

No RCS, use o comando **Implantar** para publicar uma versão do recurso de faturamento eletrônico no ambiente de serviço de destino ou aplicativo conectado.

1. No lado esquerdo da página **Recursos de Faturamento eletrônico**, selecione o recurso de faturamento eletrônico.
2. Na guia **Versões**, no lado direito da página, selecione a versão do recurso de faturamento eletrônico que você deseja implantar no ambiente de serviço ou no aplicativo conectado. A versão selecionada deve ter o status **Concluído** ou **Publicado**.
3. Selecione **Implantar** e uma das seguintes ou ambas as opções para definir o destino da implantação:

    - Aplicativo **Conectado** – A configuração fornecida pela configuração do aplicativo é gravada na instância do Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management que foi previamente associada a ela.
    - **Ambiente de serviço** – A versão do recurso de faturamento eletrônico é implantada no ambiente de serviço. O Faturamento eletrônico então estará pronto para receber e processar documentos eletrônicos enviados pelo Finance ou pelo Supply Chain Management.

> [!NOTE]
> Normalmente, você irá alterar os parâmetros do recurso ER (relatório eletrônico) que deve ser implantado no ambiente de serviço. As alterações no aplicativo conectado serão raras. Você deve implantar novas versões no aplicativo conectado somente quando alterar os parâmetros correspondentes de seu aplicativo.

Para determinar se uma versão específica de um recurso de faturamento eletrônico está implantado em um ambiente específico, examine as informações na guia **Ambientes**.

## <a name="remove-feature-versions"></a>Remover versões do recurso

No RCS, você pode selecionar **Cancelar** para remover uma versão específica do recurso de faturamento eletrônico de um ambiente de serviço, caso ele tenha sido implantado aqui.

> [!IMPORTANT]
> O botão **Cancelar** funciona somente para ambientes de serviço. Ele não remove nada do aplicativo conectado relacionado ao recurso de faturamento eletrônico.

## <a name="rebase-electronic-invoicing-features"></a>Trocar base de recursos de faturamento eletrônico

Quando um recurso de faturamento eletrônico deriva de outro, você pode selecionar **Trocar base** para atualizar o recurso derivado com as alterações feitas no recurso original.

Para alterar a base de uma versão derivada de um recurso criado por você, siga estas etapas.

1. Obtenha a versão mais recente do recurso importando-a do repositório global. Para obter mais informações, consulte [Importar recurso do repositório Global](e-invoicing-import-feature-global-repository.md).
2. Na lista de recursos, selecione o recurso a ter a base trocada.
3. Na guia **Versões**, selecione **Nova** para criar uma versão de rascunho.
4. Selecione **Trocar base**.
5. Na caixa de diálogo **Trocar base**, selecione a versão do recurso para o qual a base será trocada.
6. Selecione **OK**.
7. Revise os componentes do recurso e faça as alterações necessárias.
8. Selecione **Alterar status** para concluir o recurso com a base trocada. Quando a troca de base é concluída, você pode executar ações adicionais.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Obter a versão específica de recursos de faturamento eletrônico

Quando você cria uma nova versão de um recurso de faturamento eletrônico, o sistema cria uma cópia da versão mais recente do recurso. Para usar uma versão anterior do recurso como base para uma nova versão, selecione a versão e selecione **Obter este comando de versão**. Uma nova versão de rascunho do recurso é criada e é uma cópia da versão selecionada.
