---
title: Retail peripheral simulator
description: "Este tópico descreve a ferramenta periférica de simulador que é fornecida com Microsoft Dynamics 365 para operações de varejo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Retail peripheral simulator

Este tópico descreve a ferramenta periférica de simulador que é fornecida com Microsoft Dynamics 365 para operações de varejo.

<a name="overview"></a>Visão Geral
--------

Microsoft Dynamics 365 para o simulador operações - periférico de varejo é uma ferramenta que ajuda você teste, configurado, e solucionem problemas os dispositivos periféricos usados em ambientes de varejo. Você pode usar o simulador periférico para simplificar os testes de periféricos varejistas, e para isolar os problemas associados causados por quanto de dispositivo ou de instalação funcionando errado incorretos. O simulador periférico inclui um programa de área de trabalho que caracterize versões virtuais de dispositivos do dynamics 365 para retail - operações oferece suporte. Uma seção de cada dispositivo virtual mostra a interação entre o dispositivo e de venda manager (POS). Você também pode usá-las para fornecer a entrada válida para vários cenários POS. O simulador periférico suporta a interação entre o retail e estes dispositivos virtuais:

-   ** Impressora ** – o simulador pode mostrar periférico recebimentos configurados para impressora POS.
-   ** Linha exibição ** – você pode configurar a exibição virtual para mostrar a atividade física em uma linha.
-   ** Leitor de tarja magnética (MSR) ** – enviar eventos simulados de tarja magnética no retail simulador de periférico.
-   ** Gaveta ** – é possível simular uma físico gaveta de dinheiro.
-   ** Gaveta – 2 ** configurando uma segunda gaveta de dinheiro em simulador periférico, é possível simular os cenários que envolvem um único registro POS tenha duas turno ativos.
-   ** O scanner ** o scanner de código de barras que o simulador virtual periférico suporta pode emitir eventos do scanner de código de barras.
-   ** A escala ** – uma escala virtual permite simular a interação de itens pesados com o retail.
-   ** Teclado (PIN) do número de identificação pessoal ** – é possível simular operações de teclado do PIN. ** Observação: ** Terá suporte para implementar uma físico teclado do PIN em connector de pagamento.
-   ** A captura de subscrição ** – o simulador inclui periférico virtual um dispositivo de assinaturas de configurar para solicitar assinaturas necessárias para algumas propostas, como pagamentos de conta de cliente.

Você também pode usar o simulador periférico para simular os eventos de cunha do teclado que se originam de um scanner de código de barras e um LTM. O simulador de peripheral virtual suporta especificamente a fixação e a incorporação de objeto para dispositivos de POS (OPOS.)

## <a name="key-scenarios"></a>Cenários principais
### <a name="troubleshooting"></a>Solução de problemas

Você pode usar o simulador periférico para solucionar problemas a configuração do dispositivo. Se você não tiver o simulador periférico ou segundo um dispositivo da mesma classe, pode ser difícil determinar onde saídas derivadas. Porém, quando você tem simulador periférico, você pode configurar dispositivos virtuais, executando o mesmo código caminhos e a lógica comercial usados para dispositivos físicas. A perspectiva de simulador, periférico a principal diferença entre dispositivos virtuais e físicas dispositivos é o objeto de serviço, ou motorista do dispositivo. Para dispositivos físicas, o objeto de serviço é fornecido pelo fabricante do dispositivo. Em contraste, para o simulador periférico, os objetos de serviço são fornecidos como parte de simulador periférico. Quando o simulador periférico está funcionando apropriadamente, se um dispositivo não funciona corretamente depois que o nome do dispositivo no perfil de hardware é alterado para nome de um dispositivo real, você pode assumir que há um problema com o objeto de serviço que o informou fabricante.

### <a name="training"></a>Treinamento

Você pode usar o simulador periférico para adicionar a uma camada realista treinamento de caixa quando uma configuração de seu hardware físico não estiver disponível. Quando o simulador periférico incluído em cenários de treinamento, o caixa poderá mais eficiente interaja com o retail a fornecer entrada como verificações de código de barras de produto e passares de vale-presente, observando e recebimentos que são impressas para uma determinada transação.

### <a name="testing"></a>Testando

Você pode usar o simulador periférico para testar códigos de barras de produto, formatos de recebimento, etc, sem precisar implantar físico hardware em um ambiente virtual. Porque físico hardware não é necessária, e você não precisará implantar o POS em uma a estação de hardware ou físico em um computador, mais rápido possível testar as alterações feitas no back.

## <a name="set-up-the-peripheral-simulator"></a>Configurar o simulador periférico
### <a name="set-up-a-hardware-profile"></a>Configurar um perfil de hardware

1.  Para configurar o simulador periférico, vá ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** POS analisa ** &gt; ** ** perfis de hardware.
2.  Para criar um novo perfil, clique em novo. ** **
3.  Insira valores em ** número do perfil e ** ** descrição ** em campos.
4.  Use a tabela a seguir para configurar os dispositivos virtuais que deve ser testada. Aqui está uma explicação das colunas na tabela:
    -   ** O dispositivo ** – esta coluna indica o nome de FastTab que expandir para configurar o dispositivo.
    -   ** O tipo de dispositivo ** – esta coluna indica o valor selecionado no campo que é rotulado com o nome do dispositivo.
    -   ** O nome do dispositivo ** – esta coluna indica o valor exato inserido para o nome do dispositivo. ** Importante: ** Nomes de dispositivo que é fornecida aqui são necessários, pois a estação de hardware usa esses nomes específicos para abordar os dispositivos. Se você não usa esses nomes específicos, o dispositivo não será útil.

    | Dispositivo            | Tipo de dispositivo | Nome do dispositivo              |
    |-------------------|-------------|--------------------------|
    | Impressora           | OPOS        | MockOPOSPrinter          |
    | Display LCD de linhas      | OPOS        | MockOPOSLineDisplay      |
    | LTM               | OPOS        | MockOPOSMSR              |
    | Sacador            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | Scanner           | OPOS        | MockOPOSScanner          |
    | Balança             | OPOS        | MockOPOSScale            |
    | Teclado do PIN           | OPOS        | MockOPOSPinPad           |
    | Assinatura | OPOS        | MockOPOSSignatureCapture |

** Observação: ** Nenhum de instalação específico no perfil de hardware é exigido simular eventos de cunha de teclado do scanner de código de barras e de LTM.

### <a name="assign-the-hardware-profile-to-a-register"></a>Atribuir um perfil de hardware a um registro

1.  Depois que o perfil de hardware é criado, vai ** varejo e comércio ** &gt; ** a configuração de canal ** &gt; ** configuração POS ** &gt; ** ** registros.
2.  ** O registros POS ** lista, clique no link ** número de registradora ** campo para que o registro deve usar o simulador periférico.
3.  Clique em **Editar**.
4.  ** Em perfis **, na seção ** perfil de hardware ** campo, selecione o perfil de hardware que você criou para periféricos virtuais.
5.  Click **Save**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações no base de dados de canal

1.  Ir ** varejo e comércio ** ** &gt; varejo específicas TI ** &gt; ** o plano ** de distribuição.
2.  Selecione 1090 ** ** a agenda de distribuição.
3.  Clique ** execução agora ** para sincronizar alterações ao retail.

Depois que dados são sincronizados, o novo perfil de hardware e alterações no registro são disponíveis no base de dados do canal.

## <a name="install-the-peripheral-simulator"></a>Instalar o simulador periférico
1.  Ir ** varejo e comércio ** &gt; ** a configuração de canal ** &gt; ** configuração POS ** &gt; ** perfis POS ** &gt; ** ** perfis de hardware.
2.  Clique em download ** **, e em PeripheralSimulator ** **. ** Observação: ** Será necessário desativar bloqueador de pop-ups antes de simulador baixe o periférico.
3.  Após o download é concluído, abra ** downloads ** a pasta, clique duas vezes VirtualPeripherals.msi ** ** para iniciar o installer.
4.  Instalar o simulador periférico usando as configurações padrão.

Além do simulador periférico, instale-o objetos comuns de controle de serviços de consultoria de Monroe. Se não, o simulador periférico não funcionará corretamente. Para baixar os objetos comuns de controle, vá< para> http://monroecs.com/oposccos_current.htm.

## <a name="using-the-peripheral-simulator"></a>Usando o simulador periférico
Para iniciar o simulador, clique em Iniciar periféricos ** ** no computador, tipo simulador ** periférico varejista **, e marque o descritivo quando ele aparece nos resultados da pesquisa. Depois que você iniciar o simulador periférico, clique no nome do dispositivo para consultar dispositivos suporte. Dispositivos eles serão listados como guias no lado esquerdo da janela. Para exibir um dispositivo específico, clique na guia do dispositivo.

### <a name="line-display-capabilities"></a>Recursos exibição de linha

A exibição da linha é o primeiro dispositivo que é listado em simulador periférico. Quando a linha exiba virtual é configurada, mostra linhas de item como são digitalizados a transação POS. Além das linhas de item, a exibição mostra o total devido quando uma proposta é selecionada no POS. Também mostra o saldo devido se for inserida uma proposta mas ainda um saldo devido para a transação. Quando o retail não estiver sendo usado, uma mensagem poderá ser exibida para indicar que até está fechado. Configure a mensagem ** linha ** exibição em FastTab o perfil de hardware.

### <a name="cash-drawer-capabilities"></a>Recursos da gaveta de dinheiro

A caixa registradora seja segundo dispositivo que é listado em simulador periférico. Quando o perfil de hardware é configurado para usar gavetas virtuais de dinheiro, o retail abre a gaveta de dinheiro para o deslocamento ativo em resposta a operações de gaveta como declarações de meios, e para que o caixa possa fazer a alteração e depositar o caixa durante transações de pague-e-pegue padrão. As gavetas virtuais de caixa com os rótulos ** gaveta ** principal e secundário ** ** gaveta. Os rótulos representam gaveta gaveta 2 e o perfil de hardware, respectivamente. Quando a gaveta é fechada, uma imagem da caixa registradora fechadas será exibida, e o botão na gaveta de dinheiro fechadas é rotulado ** abrir gaveta **. Se você clicar neste botão, imagem é para substituir uma imagem de uma abrir gaveta de dinheiro para indicar que agora a gaveta é aberta. O botão em abrir gaveta de dinheiro é rotulado ** próximo ** gaveta. Várias operações no retail POS podem ocasionar a gaveta de dinheiro para abrir. A maioria de operações não podem continuar quando a caixa registradora seja aberta. Exceções são alguns procedimentos de fechamento do dia. Se o usuário do retail receberá uma mensagem de erro que indica que uma operação não pode ser realizada quando a caixa registradora seja aberta, o usuário deve fechar a gaveta virtual ou físico de dinheiro para continuar. Se um caixa registradora está marcada como ** compartilhado ** o perfil de hardware, o sistema não verifica a gaveta é fechada antes de uma operação. A operação ocorre como de costume, mesmo se a caixa registradora está aberta. Esse comportamento suporta os cenários nas gavetas de caixa são compartilhadas entre imobiliários, agentes e onde usar um associar uma caixa registradora quando outro associar realizar tarefas não relacionados em seu próprio dispositivo POS. Altera que é feito na gaveta de caixa não é auto-explicativo até turno atual está fechada e uma nova será aberta. turnos

### <a name="msr-capabilities"></a>Recursos de LTM

O simulador periférico oferece suporte robusto para operações virtuais de LTM trabalhando em modo OPOS ou em modo de cunha de teclado. O modo OPOS requer que o ltm é configurada no perfil de hardware para trabalhar como um dispositivo OPOS. Eventos de dados de cunha de teclado de enviar o modo de cunha de teclado apenas ao Microsoft Windows. Além das diferenças em de instalação, os modos de cunha OPOS e teclado de diferentes das seguintes maneiras:

-   O cliente POS habilita dispositivos OPOS para LTM cenários específicos, como os cenários de dados permitem de tarja magnética para a fidelidade ou o vale-presente.
-   Em modo de cunha do teclado, dados periféricos de cunha de teclado de enviar ao campo de simulador ativa quando dados são enviados. Esse comportamento é parecido com o comportamento que ocorre se os dados são inseridos usando um teclado. Para usar o ltm como uma cunha do teclado, o usuário deve alternar de varejo o retail MPOS) moderno (para verificar se os dados forem recebidos no campo atual. Portanto, você pode configurar um atraso, para que o usuário tem tempo para assegurar que os dados estarão enviados para o campo atual.

#### <a name="testing-gift-and-payment-card-swipes"></a>Passagens de cartão de presentes e pagamento de testes

O LTM virtual que a simulador fornece periférico também permite configurar dados específicos de LTM a cenários de teste para passagens de cartão de presentes e pagamento. Para criar um cartão, clique no botão do sinal de adição (** **+), selecione o tipo de cartão. Depois especifique o número do cartão ou acompanhar os dados que devem ser enviados ao retail, juntamente com o mês de vencimento e o ano do cartão que você está definindo. O valor selecionado ** tipo de cartão ** o campo é somente um rótulo que pode ser mapeado para um cartão. Este rótulo facilita identificar cartões quando são simulador gasto por periférico. Você pode selecionar as fichas configurados em simulador periférico usando os botões de seta para a esquerda (&lt;****) e a seta para a direita (&gt;****) acima de imagem de cartão. Você pode editar e para excluir usando fichas ** ** ** edição e exclusão ** botões ao lado de sinal de adição (+) ** ** botão.

### <a name="pin-pad"></a>Teclado do PIN

Você pode configurar o simulador de teclado do PIN para simular um teclado do PIN OPOS. Quando uma transação de (EFT) de transferência eletrônica de fundos é executada no retail e requer o PIN, a estação de hardware liga o dispositivo PIN para solicitar a entrada do PIN. Para trabalhar, o teclado do PIN em simulador periférico requer suporte connector de pagamento de TEF.

### <a name="printer"></a>Impressora

A impressora de peripheral virtual mostra apenas como recebimentos são impressos POS. Se uma operação de impressão gera vários recebimentos, poderá rolar nos recebimentos.

#### <a name="configure-receipt-printing"></a>Configure a impressão de recibo

1.  Ir ** varejo e comércio ** &gt; ** a configuração de canal ** &gt; ** configuração POS ** &gt; ** perfis POS ** &gt; ** ** perfis de hardware.
2.  Selecione o perfil de hardware que você criou para periféricos virtuais.
3.  ** ** Impressora, clique em FastTab ** ** edição.
4.  ** O recibo ID do perfil ** campo, selecione um perfil de recibo.
5.  Click **Save**.

### <a name="scale"></a>Balança

Quando um produto de escala serão adicionadas à transação POS e, em uma balança é configurada, o POS recupera o peso da escala. Na escala virtual e físico, produtos ou o peso deve ser especificado antes que o produto foram adicionadas à transação. Antes de adicionar produtos escala da transação, vá para simulador escala em periférico, e usar o sinal de adição (** **+) e os botões do sinal de menos (–) ** ** ajustar o peso da balança deve relatar. Você também pode inserir o peso desejado diretamente ** ** valor atual do campo. Você pode ajustar as unidades de peso da balança com o sinal de adição (** **+), ** **, edição e exclusão ** ** botões. Assim, as unidades podem ser especificadas com base em produtos que estão da localidade na balança é usada.

#### <a name="configure-a-scale-product"></a>Configurar um produto de balança

1.  Ir ** varejo e ** ** comércio ** &gt; ** produtos e categorias ** &gt; ** produtos lançados por categoria **.
2.  Abra o registro do produto.
3.  Selecione o produto para pesar.
4.  ** ** Varejo em FastTab, definir ** produto de escala ** a opção de ** nenhum ** a ** Sim **.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações no base de dados de canal

1.  Ir ** varejo e comércio ** ** &gt; varejo específicas TI ** &gt; ** o plano ** de distribuição.
2.  Selecione 1040 ** ** a agenda de distribuição.
3.  Clique ** execução agora ** para sincronizar alterações ao retail.

Depois que os dados forem sincronizadas, quando um produto de escala serão adicionadas à transação POS, o pos verifica a escala para peso.

### <a name="signature-capture"></a>Assinatura

Virtual o dispositivo de assinaturas solicita a fornecer uma subscrição em teclado virtual de assinaturas quando a proposta utilizada exige uma assinatura. O usuário poderá aceitar a subscrição para mostra no POS. O caixa poderá aceitar a subscrição. A subscrição em é salva com a proposta e sincronizada o back office com outros dados de transação.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Configurar uma proposta para exigir uma assinatura

1.  Ir ** varejo e comércio ** &gt; ** canais ** &gt; ** lojas ** &gt; ** ** todas as lojas.
2.  Selecione a loja.
3.  Clique em **Editar**.
4.  ** ** Clique em configuração e, em seguida, ** configuração ** na seção, clique ** ** métodos de pagamento.
5.  Clique em **Editar**.
6.  Selecione o método de pagamento que exige uma assinatura.
7.  ** ** Em geral, a seção em captura ** assinatura **, define ** use o dispositivo de assinaturas ** a opção ** Sim **.
8.  ** Valor mínimo de assinaturas ** no campo, insira o valor mínimo que deve acionar a captura de subscrição.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações no base de dados de canal

1.  Ir ** varejo e comércio ** ** &gt; varejo específicas TI ** &gt; ** o plano ** de distribuição.
2.  Selecione 1070 ** ** a agenda de distribuição.
3.  Clique ** execução agora ** para sincronizar alterações ao retail.

Depois que os dados forem sincronizadas, a proposta é usada que exige uma assinatura, o valor atende o limite de assinatura, os avisos POS para uma subscrição em virtual dispositivo de assinaturas.

## <a name="additional-configuration"></a>Configuração adicional
Você pode editar o arquivo de configuração de simulador mais periférico apropriadamente os cenários a rua que está sendo testada. Você pode encontrar o arquivo de configuração em: Carquivos de programas\\\\(x86) Microsoft Dynamics 365\\70 VirtualPeripherals\\\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. O arquivo de definição define as unidades disponíveis para testar a escala, tipos de cartão disponíveis para teste, o código de barras digita. Por exemplo, alterar os valores de texto do arquivo de configuração, você pode adicionar um novo tipo ou unidade de medida de cartão que possam ser selecionados em tempo de execução. Os novos valores aparecerão depois que o descritivo é reiniciado.

## <a name="troubleshooting"></a>Solução de problemas
As atividades do simulador periférico são registradas no simulador periférico. Você pode encontrar o log em: Carquivos de programas\\\\(x86) Microsoft Dynamics 365\\70 VirtualPeripherals\\\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. De simulador problemas periféricos relatórios também o log de eventos de O Windows, em que você pode acessar ** aplicativo e serviços registram em log ** &gt; ** Microsoft ** &gt; ** DynamicsAX **. Se alterações feitas ao perfil de hardware ou para outras áreas não são evidentes quando você usa MPOS ou o simulador periférico, verifique trabalhos do agendador distribuição usado para sincronizar os dados no base de dados do canal. Se alterações forem sincronizadas mas ainda não foram evidentes no POS, reinicie o cliente do POS. As alterações nas gavetas configurados de caixa não são efetivos até uma nova turno está criada. Portanto, se você fizer alterações nas gavetas de caixa, verifique se você fecha sempre turno existente para testar a nova configuração da gaveta de dinheiro. Ocasionalmente, o motorista de um fabricante é instalado após objetos comuns de controle de serviços de consultoria, Monroe do driver pode fazer com os objetos comuns de controle parem de funcionar corretamente. Nesse caso, você deve reinstalar objetos comuns de controle.

<a name="see-also"></a>Consulte também
--------

[Visão geral varejista] de periféricos (retail-peripherals-overview.md)


