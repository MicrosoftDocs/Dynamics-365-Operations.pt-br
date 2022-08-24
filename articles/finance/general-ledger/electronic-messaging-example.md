---
title: Configurar e executar processamento para chamar um formato de ER de exportação simples para gerar um relatório do Excel
description: Este artigo fornece um exemplo que mostra como configurar e usar mensagens eletrônicas.
author: AdamTrukawka
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.custom: ''
ms.search.form: ''
ms.openlocfilehash: 6090c45a98b672f718f89fc1d2e1c060498bb8a0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279324"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Configurar e executar processamento para chamar um formato de ER de exportação simples para gerar um relatório do Excel

[!include [banner](../includes/banner.md)]

Depois de criar seu formato de ER, o mapear para fontes de dados e o concluir, você poderá executá-lo no espaço de trabalho **Relatórios eletrônicos**. Depois que um relatório for gerado, você pode salvá-lo localmente.

Para controlar os seguintes aspectos do processo de relatórios, configure o processamento de mensagens eletrônicas:

- Registre em log informações sobre quem gerou o relatório.
- Registre em log informações sobre quando o relatório foi gerado.
- Salve os relatórios que foram gerados para períodos anteriores.

O seguinte exemplo que mostra como configurar mensagens eletrônicas para gerar um relatório baseado em um formato de ER de exportação para o Microsoft Excel. Se quiser seguir este exemplo, o formato de ER de exportação para o Excel já deve ter sido criado, mapeado para as fontes de dados e concluído. Além disso, uma sequência numérica já deverá ter ser configurada para mensagens eletrônicas.

Quando você criar o processamento, será útil principalmente se você definir as ações e os status de processamento que serão configurados. A ilustração a seguir mostra o processamento para este exemplo.

![Esquema de processamento](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Criar status da mensagem

1. Acesse **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status da mensagem**.
2. Crie os seguintes status da mensagem:

    - Nova
    - Preparado
    - Gerado

    ![Status de mensagens](media/message-statuses.png)

3. Na linha do status **Novo**, marque a caixa de seleção **Permitir exclusão** para permitir que os usuários excluam as mensagens com esse status.

## <a name="create-additional-fields"></a>Criar campos adicionais

1. Acesse **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Campos adicionais**.
2. Adicione outro campo e seus valores.
3. Defina a opção **Edição do usuário** como **Sim** para permitir que os usuários editem o campo.

![Campos adicionais](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Criar ações de processamento de mensagens

Para este exemplo, você criará as seguintes ações de processamento de mensagem:

- **Criar mensagem**
- **Atualizar como Preparado**
- **Gerar relatório**
- **Atualizar para status inicial** (opcional)

Siga estas etapas para criar as ações.

1. Acesse **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagens**.
2. Crie uma ação chamada **Criar mensagem**. Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Criar mensagem**.
3. Crie uma ação chamada **Atualizado para Preparado** e defina os seguintes campos:

    - Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Processamento de usuários no nível da mensagem**.
    - Na FastTab **Status iniciais**, no campo **Status da mensagem**, selecione **Novo**.
    - Na FastTab **Status resultantes**, no campo **Status da mensagem**, selecione **Preparado**. No campo **Tipo de resposta** , insira **Executado com êxito**.

4. Crie uma ação chamada **Gerar relatório** e defina os seguintes campos:

    - Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Exportação de relatórios eletrônicos**. No campo **Formatar mapeamento**, selecione o formato de ER de exportação. As opções são **Excel**, **XML**, **JSON**, **Texto** e **Outro**.
    - Na FastTab **Status iniciais**, no campo **Status da mensagem**, selecione **Preparado**.
    - Na FastTab **Status resultantes**, no campo **Status da mensagem**, selecione **Gerado**. No campo **Tipo de resposta** , insira **Executado com êxito**.

    ![Ação de gerar relatório](media/generate-report-action.png)

5. Opcional: para deixar que os usuários regenerem um relatório várias vezes, crie uma ação com o nome **Atualizar para status inicial** e defina os seguintes campos:

    - Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Processamento de usuários no nível da mensagem**.
    - Na FastTab **Status iniciais**, no campo **Status da mensagem**, selecione **Gerado**.
    - Na FastTab **Status de resultados**, adicione uma linha separada para cada um dos dois status de mensagem (**Preparado** e **Novo**). Para ambas as linhas, defina o campo **Tipo de resposta** como **Execução bem-sucedida**.

## <a name="electronic-message-processing"></a>Processamento de mensagem eletrônica

Para este exemplo, todas as ações devem ser configurados de forma que sejam executadas separadamente. A suposição é que cada usuário inicializará cada ação.

1. Acesse **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Processamento de mensagens eletrônicas**.
2. Adicione um registro para o processamento e adicione todas as ações definidas anteriormente e um campo adicional.
3. Opcional: na FastTab **Funções de segurança**, defina funções de segurança para que seu processamento limite o acesso para o relatório específico.
4. Acesse **Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Mensagens eletrônicas**.
5. Selecione **Nova** para criar uma mensagem. Nesse ponto, você pode adicionar datas e uma descrição. Você também pode atualizar o valor do campo adicional como necessário.

    ![Criar uma mensagem eletrônica](media/create-electronic-message.png)

    A grade da FastTab **Log de ação** é automaticamente preenchida com um log de todas as ações realizadas na mensagem.

    Agora você pode excluir ou atualizar o status da mensagem. 

6. Para atualizar o status da mensagem, selecione **Atualizar status**. No campo **Novo status** , selecione **Preparado** e, em seguida, **OK**.

    ![Atualizar o status da mensagem](media/update-status.png)

    O status de mensagem é atualizado para **Preparado**.

7. Gere o relatório selecionando **Gerar relatório**.

    O relatório é gerado, e o status da mensagem e o log de ação são atualizados.

8. Para exibir o relatório gerado, selecione o botão **Anexo** (símbolo de clipe de papel) no canto superior direito da página.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
