---
title: Verificação de qualidade
description: Este tópico fornece informações sobre o recurso Verificação de qualidade. Este recurso permite que os trabalhadores de depósito​ façam verificações por amostragem para saber a qualidade ao receberem itens para a área de doca de entrada.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: a3a565ea566dd2bf4d8c793b3340c78c9f4ed0a2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565294"
---
# <a name="quality-check"></a>Verificação de qualidade

[!include [banner](../includes/banner.md)]

O recurso *Verificação de qualidade* permite que os trabalhadores de depósito​ façam verificações por amostragem para saber a qualidade ao receberem itens para a área de doca de entrada. Essas verificações de spot são benéficas quando os trabalhadores inspecionam a embalagem ou outras partes facilmente reconhecíveis de um item. O recurso orienta os trabalhadores a verificar rapidamente se algo está obviamente com defeito ou danificado antes de colocar o estoque no local de armazenamento.

Esse recurso é uma alternativa ao processo de verificação de qualidade padrão. Ele oferece mais flexibilidade e processamento mais rápido.

Quando você usa esse recurso, a entrada e a verificação de qualidade ocorrem da seguinte maneira:

1. Quando uma remessa chega, um trabalhador do depósito registra a entrada. O trabalhador também examina uma placa de licença para registrar a localização.
1. O trabalhador faz uma verificação de qualidade rápida e registra o resultado (aprovado ou reprovado) para essa placa de licença.
1. Ocorre uma das seguintes ações:

    - Se a verificação de qualidade for aprovada, a placa de licença será aceita e dirigida a um local de recebimento, como de costume.
    - Se a verificação de qualidade falhar, a placa de licença será rejeitada e o trabalho de armazenamento existente será redirecionado para um local alternativo para uma inspeção adicional. Uma nova ordem de qualidade é criada. Para exibir a ordem de qualidade criada por meio da verificação de qualidade com falha, Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.

Esse processo também pode ser configurado de forma que todas as placas de licença verificadas sejam imediatamente desviadas para o local da verificação de qualidade.

## <a name="turn-on-the-quality-check-feature"></a>Ativar o recurso Verificação de qualidade

Para que você possa usar o recurso *Verificação de qualidade*, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Verificação de qualidade*

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configurar o recurso para o cenário de exemplo

Esta seção fornece diretrizes e um exemplo que mostra como configurar o recurso *Verificação de qualidade* e preparar dados de exemplo para o cenário de exemplo fornecido mais adiante neste tópico.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar com o [cenário de exemplo](#example-scenario) usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

### <a name="quality-check-template"></a><a name="quality-template"></a>Modelo de verificação de qualidade

O modelo de verificação de qualidade define as regras para fazer verificações por amostragem rápidas de qualidade no momento da recepção.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de verificação de qualidade**.
1. Selecione **Novo** para adicionar um modelo à grade.
1. Defina os seguintes valores para definir o novo modelo:

    - **Nome do modelo de verificação de qualidade:** *Verificação integrada*

        Insira um nome que identifique as políticas aplicadas a este modelo.

    - **Política de aceitação:** *Avisar usuário*

        Especifique se os usuários devem ser solicitados a aceitar ou rejeitar a qualidade do estoque enquanto processam o trabalho, ou se a qualidade deve ser rejeitada automaticamente. As opções disponíveis são *Rejeitar automaticamente* e *Avisar usuário*.

    - **Política de processamento de qualidade:** *Criar ordem de qualidade*

        Selecione a política que deve ser usada quando a qualidade do estoque é rejeitada. As opções a seguir estão disponíveis:

        - *Criar somente trabalho* — basta criar trabalho para facilitar a movimentação de estoque.
        - *Criar ordem de qualidade* — criar uma ordem de qualidade para facilitar testes de qualidade.

    - **Grupo de teste:** *Anexo*

        Especifique o grupo de testes que deve ser usado na ordem de qualidade criada. Os grupos de testes são configurados no módulo **Gerenciamento de estoque**.

        Deixe a opção **Texto destrutivo** desativada para o grupo de testes. Esta opção define se a amostra será destruída como parte dos testes no grupo de testes. Se um teste destrutivo for usado, o sistema gerará uma transação de estoque quando uma ordem de qualidade for criada para um item. A nova transação de estoque prevê a redução de estoque para a quantidade de teste. A redução de estoque ocorre quando a ordem de qualidade é concluída por meio da etapa de validação. A transação de estoque é identificada como uma ordem de qualidade.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Classe de trabalho — verificação de qualidade

Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de serviço que trabalhadores de depósito podem processar em um dispositivo móvel.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.
1. Selecione **Novo** para criar uma classe de trabalho.
1. No cabeçalho, defina os seguintes valores:

    - **ID da classe de trabalho:** *Verificação de QC*

        Insira um nome que identifique a classe de trabalho.

    - **Descrição:** *Verificação de QC*

        Insira uma breve descrição que indique para que a classe de trabalho será usada.

    - **Tipo de ordem de serviço:** *Qualidade na verificação de qualidade*

        Selecione o tipo de ordem de serviço que é criado pela classe de trabalho. Ao configurar o trabalho de controle de qualidade, sempre selecione *Qualidade na verificação de qualidade*.

1. Na FastTab **Tipos de local de colocação válidos**, deixe o campo **Tipo de local** em branco.

    Se você selecionar um tipo de local, limite os locais em que os itens podem ser colocados após a separação. Essa campo é usado quando uma diretiva de localização tenta resolver a localização, ou quando um trabalhador do depósito especifica manualmente a localização do item de menu do dispositivo móvel.

Para obter mais informações sobre classes de trabalho e sobre como criá-las, consulte [Criar uma classe de trabalho](tasks/create-work-class.md).

### <a name="work-template"></a>Modelo do trabalho

Os modelos de trabalho permitem definir as operações de trabalho a serem executadas no depósito. Normalmente, as operações de trabalho de depósito consistem em duas ações: um trabalhador do depósito retira o estoque disponível em um local e coloca o estoque coletado em outro local. Um modelo de trabalho para controle de qualidade define as operações de trabalho para fazer verificações de qualidade.

#### <a name="purchase-orders"></a>Ordens de Compra

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. No cabeçalho, defina o campo **Tipo de ordem de serviço** como *Ordens de compra*.
1. No Painel de Ações, selecione **Editar**.
1. Selecione um modelo de trabalho que deve incluir uma etapa de verificação de qualidade. Na seção **Visão geral**, no campo **Modelo de trabalho**, selecione *Recibo de OC 51*.
1. Na seção **Detalhes do modelo de trabalho**, observe que a grade tem duas linhas existentes: uma para *Separar* e outra para *Colocar*.
1. Na seção **Detalhes do modelo de trabalho**, selecione **Novo** para adicionar uma linha para controle de qualidade na grade. Observe que o campo **Número da linha** para a nova linha está definido como *3*.
1. Na nova linha, defina os valores a seguir. Aceite os valores padrão para os campos restantes.

    - **Tipo de trabalho:** *Verificação de qualidade*
    - **ID da classe de trabalho:** *Compra*
    - **Nome do modelo de verificação de qualidade:** *Verificação integrada*

        Selecione o ID exclusivo da classe de trabalho. Use este valor para configurar os itens de menu no dispositivo móvel e os tipos de trabalho que esses itens de menu podem processar.

1. No Painel de Ações, selecione **Salvar** para salvar o trabalho até o momento.

    Você receberá uma mensagem informativa indicando que "Inválida – Verificação de qualidade deve aparecer diretamente após uma separação". Portanto, você deve alterar o valor **Número da linha** da linha recém-adicionada.

1. Siga estas etapas para alterar o valor **Número da linha** da nova linha:

    1. Na seção **Detalhes do modelo de trabalho**, selecione a linha em que o campo **Tipo de trabalho** está definido como *Verificação de qualidade*.
    2. Selecione o botão **Mover para cima** ou **Mover para baixo** para mover a linha *Verificação de qualidade* para que fique depois da linha *Separação*.

1. No Painel de ações, selecione **Salvar**.

#### <a name="quality-in-quality-check"></a>Qualidade na verificação de qualidade

Em seguida, crie um modelo de trabalho para a verificação de qualidade.

1. No cabeçalho da página **Modelos de trabalho**, altere o valor do campo **Tipo de ordem de trabalho** para *Qualidade na verificação de qualidade*.
1. No Painel de Ações, selecione **Novo** para adicionar uma linha à grade na seção **Visão geral**.
1. Na nova linha, defina os seguintes valores:

    - **Modelo de trabalho:** *Verificação de qualidade 51*

        Insira um nome para o modelo.

    - **Descrição do modelo de trabalho:** *Verificação de qualidade 51*

1. No Painel de Ações, selecione **Salvar** para disponibilizar a seção **Detalhes do modelo de trabalho**.
1. Embora o novo modelo ainda esteja selecionado na seção **Visão geral**, selecione **Novo** na seção **Detalhes do modelo de trabalho** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tipo de trabalho:** *Separar*
    - **ID da classe de trabalho:** *Verificação de QC*

        Selecione o nome da [classe de trabalho](#work-class) criada anteriormente para o trabalho de controle de qualidade.

1. Na seção **Detalhes do modelo de trabalho**, selecione **Novo** novamente para adicionar outra linha.
1. Na nova linha, defina os seguintes valores:

    - **Tipo de trabalho:** *Colocar*
    - **ID da classe de trabalho:** *Verificação de QC*

        Selecione o nome da [classe de trabalho](#work-class) criada anteriormente para o trabalho de controle de qualidade.

1. No Painel de ações, selecione **Salvar**.

Para obter mais informações sobre modelos de trabalho, consulte [Controlar o trabalho do depósito usando modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md)

### <a name="location-directive--quality-failures"></a>Diretiva de localização – falhas de qualidade

As diretivas de localização são regras que ajudam a identificar locais de separação e armazenamento para a movimentação do estoque. Por exemplo, em uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão colocados. Você deve configurar uma regra de diretiva de localização para definir como as verificações de qualidade de falha serão tratadas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, defina o campo **Tipo de ordem de trabalho** como *Ordens de compra* para trabalhar com diretivas de localização desse tipo.
1. No Painel de Ações, selecione **Novo** para criar uma diretiva de localização para verificações de qualidade.
1. No cabeçalho, defina os seguintes valores:

    - **Número de sequência:** aceite o valor padrão.
    - **Nome:** *51 para qualidade*

1. Na FastTab **Diretivas de localização**, defina os valores a seguir. Aceite os valores padrão para os campos restantes.

    - **Tipo de trabalho:** *Colocar*
    - **Local:** *5*
    - **Depósito:** *51*

1. No Painel de Ações, selecione **Salvar** para salvar a diretiva e disponibilizar a FastTab **Linhas**.
1. Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir. Aceite os valores padrão para os campos restantes.

    - **Quantidade inicial:** *1*
    - **Quantidade final:** *1000000*

1. No Painel de Ações, selecione **Salvar** para salvar a nova linha e disponibilizar a FastTab **Ações de diretiva de localização**.
1. Enquanto a nova linha ainda estiver selecionada na FastTab **Linhas**, selecione **Novo** na FastTab **Ações de diretiva de localização** para adicionar uma linha à grade, permitindo que você configure uma ação para a linha.
1. Na nova linha, defina o campo **Nome** como *Qualidade*. Aceite os valores padrão para os campos restantes.
1. No Painel de Ações, selecione **Salvar** para disponibilizar o botão **Editar consulta** na FastTab **Ações de diretiva de localização**.
1. Com a linha recém-adicionada ainda selecionada na FastTab **Ações de diretiva de localização**, selecione **Editar consulta** para abrir uma caixa de diálogo na qual você possa editar a consulta para a ação.
1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à consulta.
1. Na nova linha, defina os seguintes valores:

    - **Tabela:** *Localizações*
    - **Tabela derivada:** *Locais*
    - **Campo:** *Localização*
    - **Critérios:** *QMS*

    A localização *QMS* é uma localização de depósito para qualidade.

1. Selecione **OK** para fechar a caixa de diálogo.
1. Você deve alterar a sequência das diretivas de localização de ordens de compra para o depósito *51*. Salve a nova diretiva de localização *51 para qualidade*, atualize a página e selecione a diretiva de localização na lista. Em seguida, use os botões **Mover para cima** e **Mover para baixo** no Painel de Ações para colocar a diretiva de localização para o depósito *51* na ordem a seguir. (Antes de selecionar **Mover para cima** ou **Mover para baixo**, você deve selecionar uma diretiva de localização na lista.)

    1. 51 para qualidade
    2. OC Direta 51
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Itens de menu do dispositivo móvel

Configure um item de menu para que os dispositivos móveis possam executar a função **Verificação de Qualidade**.

#### <a name="purchase-putaway"></a>Armazenamento de compra

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Na lista, selecione o item de menu **Armazenamento de compra**.
1. No Painel de Ações, selecione **Editar**.
1. Na seção **Classes de trabalho**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **ID da classe de trabalho:** *Verificação de QC*

        Insira o nome da [classe de trabalho](#work-class) criada anteriormente para o trabalho de controle de qualidade.

    - **Tipo de ordem de serviço:** *Qualidade na verificação de qualidade*

1. No Painel de ações, selecione **Salvar**.

#### <a name="purchase-order-line-receiving"></a>Recebimento da linha da ordem de compra

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Nome do item de menu:** *Recebimento da linha da OC*
    - **Título:** *Recebimento da linha da OC*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Não*

1. Na FastTab **Geral**, defina os valores a seguir. Aceite os valores padrão para os campos restantes.

    - **Processo de criação de trabalho:** *Recebimento e armazenamento da linha da ordem de compra*
    - **Gerar placa de licença:** *Sim*
    - **Modelo de trabalho:** *Recibo de OC 51*

1. No Painel de ações, selecione **Salvar**.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Adicionar o item de menu ao menu de um dispositivo móvel

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. No painel esquerdo, selecione o menu **Entrada**.
1. No Painel de Ações, selecione **Editar**.
1. Na coluna **Menus e itens de menu disponíveis**, selecione o novo item de menu **Recebimento da linha da OC**.
1. Selecione o botão de seta para a direita para mover **Recebimento da linha da OC** para a coluna **Estrutura de menu**.
1. Na coluna **Estrutura de menu**, selecione **Recebimento da linha da OC** e, depois, selecione o botão de seta para cima ou seta para baixo para mover o item de menu para a posição desejada no menu dispositivo móvel.
1. No Painel de ações, selecione **Salvar**.

## <a name="example-scenario"></a><a name="example-scenario"></a>Cenário de exemplo

Após disponibilizar todos os dados de exemplo descritos anteriormente e configurá-los, você poderá trabalhar neste cenário para testar o recurso *Verificação de qualidade*. Os valores que são mostrados neste cenário pressupõem que você está trabalhando com os dados de demonstração padrão, que você selecionou a entidade legal **USMF** e preparou os registros de exemplo descritos anteriormente neste tópico. Esse cenário também serve como exemplo para mostrar como o recurso pode ser usado em uma configuração de produção.

### <a name="create-a-purchase-order"></a>Criar uma ordem de compra

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:

    - **Conta do fornecedor:** *104*
    - **Depósito:** *51*

1. Selecione **OK** para fechar a caixa de diálogo e abrir a nova ordem de compra.
1. Na FastTab **Linhas de ordem de compra**, a grade contém uma linha nova, em branco. Nessa linha, defina os seguintes valores:

    - **Número de item:** *M9203*
    - **Quantidade:** *3*
    - **Unidade:** *PL*

1. No Painel de ações, selecione **Salvar**.

### <a name="process-quality-check-receiving"></a>Recebimento da verificação de qualidade do processo

Depois que a ordem de compra for criada, ela poderá ser recebida usando o item de menu **Recebimento da linha da OC** e a funcionalidade do recurso *Verificação de qualidade*.

#### <a name="receive-pallet-1"></a>Receber palete 1

1. Entre no aplicativo móvel do Gerenciamento de Depósito como um usuário para o depósito *51*. (Insira *51* como a ID do usuário e *1* como a senha.)
1. Acesse **Entrada \> Recebimento da linha da OC**.
1. No campo **PONUM**, insira o número da ordem de compra.
1. Confirme o número da ordem de compra.
1. No campo **LINENUM**, insira o número da linha da ordem de compra que está sendo recebida. Como a ordem tem apenas uma linha neste cenário, você inserirá *1* no campo **LINENUM** para cada etapa de recebimento.
1. Confirme o número da linha.
1. No campo **QTD**, insira a quantidade a ser recebida. Como a ordem de compra é para três paletes (*PL*) neste cenário e há três etapas de recebimento, você inserirá *1* no campo **QTD** para cada etapa de recebimento.
1. Confirme a quantidade.

    A página **Verificação de qualidade** que aparece não tem campos de entrada. Ela tem apenas o botão de confirmação (marca de seleção) na parte inferior e o botão de menu (**≡**) na parte superior. (Às vezes, o botão de menu é referenciado como hambúrguer ou botão de hambúrguer.) Para agilizar o processo de verificação de qualidade, quando o palete passa pela verificação de qualidade, o usuário apenas confirma a página **Verificação de qualidade**.

    ![Página Verificação de qualidade.](media/quality-check.png "Página Verificação de qualidade")

1. Selecione o botão de confirmação para passar a verificação de qualidade para o palete 1 da linha 1.

    A página **Ordens de compra: colocar** que aparece mostra detalhes do trabalho de colocação:

    - **LOC:** a localização determinada do sistema

        Essa localização é o local de armazenamento designado para recebimento da ordem de compra.

    - **LP:** a ID da placa de licença gerada pelo sistema
    - **Item:** *M9203*
    - **Qtd:** *1 PL: 100 cada*

    A descrição do item também é mostrada.

1. Confirme o trabalho de armazenamento.

    Na página **Tarefa** para recebimento de linha da ordem de compra, você recebe uma mensagem "Trabalho Concluído". O campo **LINENUM** está disponível para que você comece a receber o próximo palete.

#### <a name="receive-pallet-2"></a>Receber palete 2

Neste cenário, o palete 2 será rejeitado.

1. No campo **LINENUM**, insira *1* e confirme o número da linha.
1. O campo **QTD** agora está disponível. Insira *1* e confirme a quantidade.

    A página **Verificação de qualidade** é exibida. Para esse recebimento, o palete será rejeitado para qualidade e será colocado no local de qualidade *QMS*.

1. Selecione o botão de menu (**≡**) na parte superior da página e, no menu, selecione **Rejeitar**.
1. Na página **Tarefa**, insira **QMS** como o local *Colocar* para onde o palete será enviado para inspeção adicional.

    A página **Qualidade na verificação de qualidade: colocar** que aparece mostra detalhes do trabalho de colocação:

    - **LOC:** *QMS*

        Essa localização é o local de armazenamento designado para recebimento da qualidade rejeitada.

    - **LP:** a ID da placa de licença gerada pelo sistema
    - **Item:** *M9203*
    - **Qtd:** *1 PL: 100 cada*

    A descrição do item também é mostrada.

1. Confirme o trabalho de armazenamento.

    Na página **Tarefa** para recebimento de linha da ordem de compra, você recebe uma mensagem "Trabalho Concluído". O campo **LINENUM** está disponível para que você comece a receber o próximo palete.

Você acabou de concluir a verificação de qualidade e criou uma ordem de qualidade para o palete rejeitado. Para exibir a ordem que foi criada, Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.

O teste da ordem de qualidade pode ser processado agora. O teste de qualidade não é abordado neste tópico.

Para obter mais informações sobre o gerenciamento de qualidade, consulte [Visão geral do gerenciamento de qualidade](../inventory/enable-quality-management.md)

#### <a name="receive-pallet-3"></a>Receber palete 3

Neste cenário, o palete 3 será aceito.

1. No campo **LINENUM**, insira *1* e confirme o número da linha.
1. O campo **QTD** agora está disponível. Insira *1* e confirme a quantidade.

    A página **Verificação de qualidade** é exibida. Para esse recebimento, o palete será aceito para qualidade e será colocado em um local de armazenamento em massa.

1. Selecione o botão de confirmação para passar a verificação de qualidade.

    A página **Ordens de compra: colocar** que aparece mostra detalhes do trabalho de colocação:

    - **LOC:** a localização determinada do sistema

        Essa localização é o local de armazenamento designado para recebimento da ordem de compra.

    - **LP:** a ID da placa de licença gerada pelo sistema
    - **Item:** *M9203*
    - **Qtd:** *1 PL: 100 cada*

    A descrição do item também é mostrada.

1. Confirme o trabalho de armazenamento.

    Na página **Tarefa** para recebimento de linha da ordem de compra, você recebe uma mensagem "Trabalho Concluído". O campo **LINENUM** está disponível para que você comece a receber o próximo palete.

1. Selecione o botão de menu (**≡**) na parte superior da página e, no menu, selecione **Cancelar** para voltar ao menu.

Agora você pode fechar o aplicativo móvel.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]