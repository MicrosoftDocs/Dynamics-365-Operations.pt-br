---
title: Suporte ao recurso de imposto para a ordens de transferência
description: Este tópico explica o novo suporte a recursos de imposto para ordens de transferência usando o serviço de cálculo de imposto.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1c47c327841b8c712220e440e2aa6b4fe2b31b4a1ccd03dc0a200dbeb7394071
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721680"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Suporte ao recurso de imposto para a ordens de transferência

[!include [banner](../../includes/banner.md)]

Este tópico fornece informações sobre cálculo de impostos e integração de lançamento em ordens de transferência. Essa funcionalidade permite que você defina o cálculo e o lançamento de impostos em ordens de transferência para transferências de estoque. Sob as regulamentações de imposto sobre valor agregado (IVA) da União Europeia (UE), as transferências de estoque são consideradas de fornecimento e aquisição interna na comunidade.

Para configurar e usar esse recurso, você deve seguir três etapas principais:

1. **Configuração do RCS:** no serviço de configuração regulatória, defina o recurso de imposto, os códigos de imposto e a aplicabilidade dos códigos de imposto para determinar o código de imposto em ordens de transferência.
2. **Configuração de finanças:** no Microsoft Dynamics 365 Finance, ative o recurso **Imposto em ordem de transferência**, configure os parâmetros do serviço de imposto do estoque e defina os principais parâmetros de imposto.
3. **Configuração de estoque:** defina a configuração de estoque para transações de ordem de transferência.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Configurar o RCS para transações de ordem de transferência e imposto

Siga estas etapas para configurar o imposto envolvido em uma ordem de transferência. No exemplo mostrado, a ordem de transferência é dos Países Baixos para a Bélgica.

1. Na página **Recursos de impostos**, na guia **Versões**, selecione o rascunho da versão do recurso e selecione **Editar**.

    ![Depois de selecionar Editar.](../media/tax-feature-support-01.png)

2. Na página **Configuração dos recursos de impostos**, na guia **Códigos de impostos**, selecione **Adicionar** para criar códigos de impostos. Nesse exemplo, três códigos de imposto são criados: **NL-Exempt**, **BE-RC-21** e **BE-RC+21**.

    - Quando uma ordem de transferência é enviada de um depósito nos Países Baixos, o código de imposto isento de IVA dos Países Baixos (**NL-Exempt**) é aplicado.
      
        Crie o código de imposto **NL-Exempt**.
        1. Selecione **Adicionar**, insira o código **NL-Exempt** no campo **Código de imposto**.
        2. Selecione **Por valor líquido** no campo **Componente de imposto**.
        3. Selecione **Salvar**.
        4. Selecione **Adicionar** na tabela **Taxa**.
        5. Altere o campo **É Isento** para **Sim** na seção **Geral**.

        ![Código de imposto NL-Exempt.](../media/tax-feature-support-02.png)

    - Quando uma ordem de transferência é recebida em um depósito na Bélgica, o mecanismo de cobrança revertido é aplicado usando os códigos de imposto **BE-RC-21** e **BE-RC+21**.
        
        Crie o código de imposto **BE-RC-21**.      
        1. Selecione **Adicionar**, insira o código **BE-RC-21** no campo **Código de imposto**.
        2. Selecione **Por valor líquido** no campo **Componente de imposto**.
        3. Selecione **Salvar**.
        4. Selecione **Adicionar** na tabela **Taxa**.
        5. Insira **-21** no campo **Taxa tributária**.
        6. Altere o campo **É Encargo Reverso** para **Sim** na seção **Geral**.
        7. Selecione **Salvar**.

        ![Código de imposto BE-RC-21 para cobranças revertidas.](../media/tax-feature-support-03.png)
        
        Crie o código de imposto **BE-RC+21**.
        1. Selecione **Adicionar**, insira o código **BE-RC-21** no campo **Código de imposto**.
        2. Selecione **Por valor líquido** no campo **Componente de imposto**.
        3. Selecione **Salvar**.
        4. Selecione **Adicionar** na tabela **Taxa**.
        5. Insira **21** no campo **Taxa tributária**.
        6. Selecione **Salvar**.

        ![Código de imposto BE-RC+21 para cobranças revertidas.](../media/tax-feature-support-04.png)

3. Defina a aplicabilidade dos códigos de imposto.

    1. Selecione **Gerenciar colunas** e selecione as colunas que devem ser usadas para criar a tabela de aplicabilidade.

        > [!NOTE]
        > Adicionar as colunas **Processo comercial** e **Direções de imposto** à tabela. As duas colunas são essenciais para a funcionalidade do imposto em ordens de transferência.

    2. Inclua regras de aplicabilidade. Não deixe os campos **Códigos de imposto**, **Grupo de impostos** e **Grupo de impostos sobre o item** em branco.
        
        Inclua uma nova regra para a remessa da ordem de transferência.
        1. Selecione **Adicionar** na tabela **Regras de aplicabilidade**.
        2. No campo **Processo comercial**, selecione **Estoque** para tornar a regra aplicável para uma ordem de transferência.
        3. No campo **Enviar do país/região**, insira **NLD**.
        4. No campo **Enviar para país/região**, insira **BEL**.
        5. No campo **Direção de imposto**, selecione **Saída** para tornar a regra aplicável à remessa da ordem de transferência.
        6. No campo **Códigos de imposto**, selecione **NL-Exempt**.
        7. No campo **Grupo de impostos** e no **Grupo de impostos sobre o item**, insira o grupo de impostos sobre vendas relacionado e o grupo de impostos sobre vendas do item que são definidos no seu sistema financeiro.
        
        Inclua outra regra para o recebimento da ordem de transferência.
        1. Selecione **Adicionar** na tabela **Regras de aplicabilidade**.
        2. No campo **Processo comercial**, selecione **Estoque** para tornar a regra aplicável para uma ordem de transferência.
        3. No campo **Enviar do país/região**, insira **NLD**.
        4. No campo **Enviar para país/região**, insira **BEL**.
        5. No campo **Direção de imposto**, selecione **Entrada** para tornar a regra aplicável ao recebimento da ordem de transferência.
        6. No campo **Códigos de imposto**, selecione **BE-RC+21** e **BE-RC-21**.
        7. No campo **Grupo de impostos** e no **Grupo de impostos sobre o item**, insira o grupo de impostos sobre vendas relacionado e o grupo de impostos sobre vendas do item que são definidos no seu sistema financeiro.

        ![Regras de aplicabilidade.](../media/image5.png)

4. Conclua e publique a nova versão do recurso de imposto.

    [![Alteração do status da nova versão.](../media/image6.png)](../media/image6.png)

## <a name="set-up-finance-for-transfer-order-transactions"></a>Configure as Finanças para transações de ordem de transferência e imposto

Siga estas etapas para habilitar e configurar os impostos para ordens de transferência.

1. Em Finanças, acesse **Espaços de trabalho** \> **Gerenciamento do recurso**.
2. Na lista, localize e selecione o recurso **Imposto em ordem de transferência** e selecione **Habilitar agora** para ativá-lo.

    > [!IMPORTANT]
    > O recurso **Imposto em ordem de transferência** depende totalmente do serviço de imposto. Portanto, ele pode ser ativado somente após a instalação do serviço de imposto.

    ![Recurso de impostos em ordem de transferência.](../media/image7.png)

3. Habilite o serviço de imposto e selecione o processo comercial **Estoque**.

    > [!IMPORTANT]
    > Você deve concluir esta etapa para cada entidade legal no departamento financeiro em que deseja que o serviço de imposto e a funcionalidade do imposto sobre as ordens de transferência estejam disponíveis.

    1. Acesse **Imposto** \> **Configuração** \> **Configuração do imposto** \> **Configuração do serviço de imposto**.
    2. No campo **Processo comercial**, selecione **Estoque**.

    ![Configuração do campo Processo comercial.](../media/image8.png)

4. Verifique se o mecanismo de reversão da cobrança está configurado. Acesse **Contabilidade** \> **Configuração** \> **Parâmetros** e, na guia **Reverter cobrança**, verifique se a opção **Habilitar a reversão da cobrança** está definida para **Sim**.

    ![Habilite a opção de reversão da cobrança.](../media/image9.png)

5. Verifique se os códigos de imposto relacionados, grupos de impostos, grupos de impostos do item e números de registro do IVA foram configurados em Finanças de acordo com a orientação do serviço de imposto.
6. Configure uma conta de trânsito provisória. Essa etapa é necessária apenas quando o imposto aplicado a uma ordem de transferência não é aplicável a um mecanismo isento de imposto ou de cobrança revertida.

    1. Acesse **Imposto** \> **Configuração** \> **Imposto sobre vendas** \> **Grupos de lançamento da razão**.
    2. No campo **Trânsito provisório**, selecione uma conta contábil.

    ![Selecionar uma conta de trânsito provisória.](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Configure o estoque básico para transações de ordem de transferência e imposto

Siga estas etapas para configurar o inventário básico e habilitar transações de ordem de transferência.

1. Crie sites de "enviar de" e "enviar para" seus depósitos em diferentes países ou regiões e adicione o endereço principal para cada site.

    1. Acesse **Gerenciamento do depósito** \> **Configuração** \> **Depósito** \> **Locais**.
    2. Selecione **Novo** para criar o local que será atribuído a um depósito posteriormente.
    3. Repita a etapa 2 para todos os outros locais que você criar.

    > [!NOTE]
    > Um dos locais deve ser nomeado como **Trânsito**. Nas próximas etapas deste procedimento, você atribuirá esse local ao depósito de trânsito para que os comprovantes de estoque relacionados a impostos possam ser lançados em transações de "envio" e "recebimento" para ordens de transferência. O endereço do local de trânsito é irrelevante para o cálculo de imposto. Portanto, você pode deixá-lo em branco.

    ![Definição dos locais.](../media/image11.png)

2. Crie depósitos de "envio de", trânsito e "envio para". As informações de endereço mantidas em um depósito substituirão o endereço do local durante o cálculo do imposto.

    1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Depósito** \> **Depósitos**.
    2. Selecione **Novo** para criar um depósito e atribuí-lo ao local correspondente.
    3. Repita a etapa 2 para criar um depósito para cada local, conforme necessário.

    ![Definição dos depósitos.](../media/image12.png)

    > [!NOTE]
    > No caso de um depósito de "envio para", é necessário selecionar um depósito de trânsito no campo **Depósito de trânsito** para as transações de ordem de transferência.
    >
    > ![Escolha de um depósito de trânsito.](../media/image13.png)

3. Verifique se a configuração do lançamento do estoque está definida para transações de ordem de transferência.

    1. Acesse **Gerenciamento de estoque** \> **Configurar** \> **Lançamento** \> **Lançamento**.
    2. Na guia **Estoque**, verifique se uma conta contábil está configurada para lançamento de **Saída de estoque** e **Recebimento do estoque**.

        ![Configuração dos lançamentos Saída de estoque e Recebimento de estoque.](../media/image14.png)

    3. Verifique se uma conta contábil está configurada para lançamento **A pagar entre unidades**.

        ![Configuração do lançamento A pagar entre unidades.](../media/image15.png)

    4. Verifique se uma conta contábil está configurada para lançamento **A receber entre unidades**.

        ![Configuração do lançamento A receber entre unidades.](../media/image16.png)
