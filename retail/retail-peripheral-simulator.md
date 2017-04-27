---
title: "Simulador periférico de varejo"
description: "Este tópico descreve a ferramenta de simulação periférica fornecida com o Microsoft Dynamics 365 para Operações - Varejo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
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

# <a name="retail-peripheral-simulator"></a>Simulador periférico de varejo

[!include[banner](includes/banner.md)]


Este tópico descreve a ferramenta de simulação periférica fornecida com o Microsoft Dynamics 365 para Operações - Varejo.

<a name="overview"></a>Visão Geral
--------

O simulador periférico do Microsoft Dynamics 365 para Operações - Varejo é uma ferramenta que ajuda você a configurar, testar e solucionar problemas de dispositivos periféricos usados em ambientes de varejo. Você pode usar o simulador periférico para agilizar os testes com periféricos de varejo, e para isolar problemas causados por configurações incorretas ou por drivers de dispositivo que apresentem mau funcionamento. O simulador periférico inclui um programa que contém versões virtuais de dispositivos suportados pelo Dynamics 365 para Operações - Varejo. Uma seção para cada dispositivo virtual mostra a interação entre o dispositivo e o ponto de venda (PDV) do varejo. Você também pode usá-las para fornecer entradas válidas para vários cenários de PDV. O simulador periférico suporta interações entre o PDV e os seguintes dispositivos virtuais:

-   **Impressora** – O simulador periférico pode exibir recibos configurados para uma impressora de PDV.
-   **Display de linhas** – Você pode configurar um display de linhas virtual para exibir as atividades em um display de linhas físico.
-   **Leitor de tarja magnética (LTM)** – Você pode enviar eventos simulados de tarja magnética para o PDV através do simulador periférico.
-   **Gaveta** – Você pode simular uma gaveta de dinheiro física.
-   **Gaveta 2** – Ao configurar uma segunda gaveta de dinheiro no simulador periférico, é possível simular cenários que envolvam um único registrador de PDV com dois turnos ativos.
-   **Scanner** – O leitor de código de barras virtual suportado pelo simulador periférico pode emitir eventos de leitura de códigos de barras.
-   **Balança** – Uma balança virtual permite que você simule a interação de itens pesados com o PDV.
-   **Número de identificação pessoal (PIN)** – Você pode simular operações em um teclado de PIN. **Observação:** Você deve implementar o suporte para um teclado de PIN físico através do conector de pagamento.
-   **Captura de assinatura** – O simulador periférico inclui um dispositivo virtual de captura de assinatura que pode ser configurado para solicitar assinaturas necessárias para algumas propostas, como pagamentos de conta de cliente.

Você também pode usar o simulador periférico para simular eventos via teclado originados de um leitor de código de barras e LTM. O simulador periférico virtual suporta especificamente a Conexão e Integração de Objetos para dispositivos de PDV (OPOS) de Varejo.

## <a name="key-scenarios"></a>Cenários chave
### <a name="troubleshooting"></a>Solução de problemas

Você pode usar o simulador periférico para solucionar problemas na configuração do dispositivo. Se você não tiver o simulador periférico ou um outro dispositivo da mesma classe, pode ser difícil determinar a origem dos problemas. Por outro lado, tendo o simulador periférico você pode configurar dispositivos virtuais e executar os mesmos caminhos de código e lógica comercial utilizados em dispositivos físicos. Do ponto de vista do simulador periférico, a principal diferença entre dispositivos virtuais e físicos é o objeto de serviço, ou o driver do dispositivo. Para dispositivos físicos, o objeto de serviço é fornecido pelo fabricante do dispositivo. Por outro lado, para o simulador periférico, os objetos de serviço são fornecidos como parte do próprio simulador. Quando o simulador periférico está funcionando corretamente, se um dispositivo não funciona corretamente depois que o nome do dispositivo é alterado no perfil de hardware para o nome de um dispositivo real, você pode assumir que há um problema com o objeto de serviço que o fabricante forneceu.

### <a name="training"></a>Treinamento

Você pode usar o simulador periférico para adicionar uma camada realista ao treinamento de caixa quando uma configuração de hardware físico não estiver disponível. Quando o simulador periférico é incluído em cenários de treinamento, o caixa pode interagir de modo mais eficiente com o PDV fornecendo entradas como leituras de código de barras do produto e troca de cartões de presente, e também observando qual recibo é impresso para cada transação específica.

### <a name="testing"></a>Testando

Você pode usar o simulador periférico para testar códigos de barras de produtos, formatos de recibos, e assim por diante, sem a necessidade de implantar hardware físico em um ambiente virtual. Uma vez que não é necessário hardware físico, e você não precisa implantar um cliente PDV em uma estação de hardware ou computador físico, você pode testar mudanças realizadas no back office de maneira mais rápida.

## <a name="set-up-the-peripheral-simulator"></a>Configurar o simulador periférico
### <a name="set-up-a-hardware-profile"></a>Configurar um perfil de hardware

1.  Para configurar o simulador periférico, vá para **Comércio e Varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Para criar um novo perfil, clique em **Novo**.
3.  Insira valores nos campos **Número do perfil** e **Descrição**.
4.  Use a tabela a seguir para configurar os dispositivos virtuais que devem ser testados. Esta é uma explicação sobre as colunas da tabela:
    -   **Dispositivo** – Essa coluna fornece o nome da Guia Rápida que você utiliza para configurar o dispositivo.
    -   **Tipo de dispositivo** – Essa coluna fornece o valor que você seleciona no campo rotulado com o nome do dispositivo.
    -   **Nome do dispositivo** – Essa coluna fornece o valor exato inserido para o nome do dispositivo. **Importante:** Os nomes dos dispositivos fornecidos aqui são necessários, pois a estação de hardware usa esses nomes específicos para dirigir-se aos dispositivos. Se você não usar esses nomes específicos, o dispositivo não será utilizável.

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

**Observação:** Nenhuma configuração específica no perfil de hardware é exigida para simular eventos via teclado do leitor de código de barras e LTM.

### <a name="assign-the-hardware-profile-to-a-register"></a>Atribuir o perfil de hardware a uma registradora

1.  Assim que o perfil de hardware for criado, vá para **Comércio e varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Registradoras**.
2.  Na lista **Registradoras de PDV**, clique no link do campo **Número da registradora** referente a registradora que deve usar o simulador periférico.
3.  Clique em **Editar**.
4.  Na seção **Perfis**, no campo **Perfil de hardware**, selecione o perfil de hardware criado para periféricos virtuais.
5.  Clique em **Salvar**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações na base de dados do canal

1.  Vá para **Comércio e varejo** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
2.  Selecione a agenda de distribuição **1090**.
3.  Clique em **Executar agora** para sincronizar alterações no PDV.

Assim que os dados forem sincronizados, o novo perfil de hardware e as alterações na registradora estarão disponíveis na base de dados do canal.

## <a name="install-the-peripheral-simulator"></a>Instalar o simulador periférico
1.  Vá para **Comércio e varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Clique em **Baixar**, e em seguida clique em **PeripheralSimulator**. **Observação:** Você deve desativar o bloqueio de pop-ups antes de baixar o simulador periférico.
3.  Assim que terminar de baixar, abra a pasta **Downloads**, e clique duas vezes no **VirtualPeripherals.msi** para iniciar o instalador.
4.  Instale o simulador periférico utilizando as configurações padrão.

Além do simulador periférico, você deve instalar os objetos de controle usuais da Monroe Consulting Services. Caso contrário, o simulador periférico não funcionará corretamente. Para baixar os objetos de controle usuais, vá para <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Utilizando o simulador periférico
Para iniciar o simulador periférico, clique em **Iniciar** no seu computador, digite **Simulador periférico de varejo**, e selecione o aplicativo quando ele aparecer nos resultados da busca. Depois que iniciar o simulador periférico, clique em um nome de dispositivo para consultar os dispositivos suportados. Esses dispositivos estarão listados como abas no lado esquerdo da janela. Para exibir um dispositivo específico, clique na aba do dispositivo desejado.

### <a name="line-display-capabilities"></a>Recursos do display de linhas

O display de linhas é o primeiro dispositivo listado no simulador periférico. Quando o display de linhas virtual é configurado, ele exibe itens assim que são escaneados durante a transação no PDV. Além dos itens, o display exibe o total devido quando uma proposta é selecionada no PDV. Ele também exibe o saldo devido caso uma proposta seja inserida mas ainda exista um saldo devido para a transação. Quando o PDV não está sendo usado, uma mensagem pode ser exibida para indicar que o caixa está fechado. Você deve configurar a mensagem na Guia Rápida **Display de linhas** no perfil de hardware.

### <a name="cash-drawer-capabilities"></a>Recursos da gaveta de dinheiro

A gaveta de dinheiro é o segundo dispositivo listado no simulador periférico. Quando o perfil de hardware é configurado para usar gavetas de dinheiro virtuais, o PDV abre a gaveta de dinheiro do turno ativo em resposta a operações da gaveta como declarações de propostas, para que o caixa possa alterar ou depositar dinheiro durante transações padrão de "cash-and-carry". As gavetas de dinheiro virtuais possuem os rótulos **Gaveta principal** e **Gaveta secundária**. Esses rótulos representam, respectivamente, a Gaveta e a Gaveta 2 no perfil de hardware. Quando uma gaveta é fechada, uma imagem de uma gaveta de dinheiro fechada é exibida, e o botão na gaveta de dinheiro fechada recebe o rótulo **Abrir gaveta**. Se você clicar neste botão, a imagem é substituída pela imagem de uma gaveta de dinheiro aberta para indicar que agora a gaveta está aberta. O botão da gaveta de dinheiro aberta recebe o rótulo **Fechar gaveta**. Diversas operações no PDV podem fazer com que a gaveta de dinheiro abra. A maioria das operações não pode continuar enquanto a gaveta de dinheiro estiver aberta. As exceções são alguns procedimentos de final do dia. Se o usuário do PDV receber uma mensagem de erro dizendo que uma operação não pode ser realizada enquanto a gaveta de dinheiro estiver aberta, o usuário deve fechar a gaveta de dinheiro física ou virtual para proceder. Se uma gaveta de dinheiro está marcada como **Compartilhada** no perfil de hardware, o sistema não verifica se a gaveta está fechada antes de uma operação. A operação continua como de costume, mesmo que a gaveta de dinheiro esteja aberta. Esse comportamento suporta cenários onde gavetas de dinheiro são compartilhadas entre associados de vendas, e onde um associado utiliza uma gaveta de dinheiro enquanto outro associado realiza tarefas não relacionadas em seu próprio dispositivo de PDV. As alterações realizadas na gaveta de dinheiro não são evidentes até que o turno atual seja encerrado e um novo turno comece.

### <a name="msr-capabilities"></a>Recursos LTM

O simulador periférico oferece suporte robusto para operações virtuais de LTM trabalhando tanto em modo OPOS como em modo via teclado. O modo OPOS requer que o LTM seja configurado no perfil de hardware para trabalhar como um dispositivo OPOS. O modo via teclado apenas envia eventos de dados via teclado ao Microsoft Windows. Além das diferenças na configuração, os modos OPOS e via teclado diferem nos seguintes aspectos:

-   O cliente PDV habilita dispositivos LTM no modo OPOS em cenários específicos, como cenários que permitam a entrada de dados de cartões presente ou fidelidade.
-   No modo via teclado, o simulador periférico envia dados via teclado ao campo ativo no momento em que o dado é enviado. Esse comportamento é semelhante ao comportamento que ocorre se os dados são inseridos usando um teclado. Para usar o LTM no modo via teclado, o usuário deve mudar para PDV de Varejo Moderno (MPOS) para garantir que os dados sejam recebidos nos campos corretos. Portanto, você pode configurar um atraso, para que o usuário tenha tempo para garantir que os dados serão enviados aos campos corretos.

#### <a name="testing-gift-and-payment-card-swipes"></a>Testando passagens de cartão de pagamento e cartão presente

O LTM virtual que a simulador periférico fornece também permite configurar dados específicos de LTM para testar cenários de passagens de cartões de pagamento ou de presente. Para criar um cartão, clique no botão com o sinal de mais (**+**), e selecione o tipo de cartão. Depois especifique o número do cartão ou rastreie dados que deveriam ser enviados ao PDV, junto com a data de validade do cartão que está sendo definido. O valor selecionado no campo **Tipo de cartão** é apenas um rótulo que pode ser mapeado a um cartão. Este rótulo facilita a identificação de cartões quando são passados através do simulador periférico. Você pode selecionar cartões que foram configurados no simulador periférico utilizando os botões das setas esquerda (**&lt;**) e direita (**&gt;**) acima da imagem do cartão. Você pode editar e deletar cartões utilizando os botões **Editar** e **Deletar** próximos ao botão com o sinal de mais (**+**).

### <a name="pin-pad"></a>Teclado do PIN

Você pode configurar o simulador de teclado de PIN para simular um teclado de PIN OPOS. Quando uma transação de transferência eletrônica de fundos (TEF) é realizada no PDV e solicita a entrada do PIN, a estação de hardware aciona o dispositivo PIN para se preparar para a entrada do PIN. Para funcionar, o teclado de PIN no simulador periférico precisa de suporte ao conector de pagamento TEF.

### <a name="printer"></a>Impressora

A impressora periférica virtual apenas exibe recibos assim que eles são impressos no PDV. Se uma operação de impressão produz múltiplos recibos, você pode percorrer todos eles.

#### <a name="configure-receipt-printing"></a>Configurar a impressão de recibos

1.  Vá para **Comércio e varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Selecione o perfil de hardware criado para periféricos virtuais.
3.  Na Guia Rápida **Impressora**, clique em **Editar**.
4.  No campo **ID de perfil do recibo**, selecione um perfil de recibo.
5.  Clique em **Salvar**.

### <a name="scale"></a>Balança

Quando um produto de balança é adicionado à transação do PDV, e existe uma balança configurada, o PDV obtém o peso através da balança. Para ambas as balanças virtual e física, o produto ou peso deve ser especificado antes que o produto seja adicionado à transação. Antes de adicionar o produto de balança à transação, vá até a balança no simulador periférico e use os botões com sinais de mais (**+**) e menos (**–**) para ajustar o peso que a balança deve apresentar. Você também pode inserir o peso desejado diretamente no campo **Valor atual**. Você pode ajustar as unidades de peso da balança usando o sinal de mais (**+**), e os botões **Editar** e **Deletar**. Dessa maneira, as unidades podem ser especificadas com base nos produtos que estão sendo pesados e no local em que a balança é usada.

#### <a name="configure-a-scale-product"></a>Configurar um produto de balança

1.  Vá para **Comércio e** **varejo** &gt; **Produtos e categorias** &gt; **Produtos lançados por categoria**.
2.  Abra o registro do produto.
3.  Selecione o produto a ser pesado.
4.  Na Guia Rápida **Varejo**, defina a opção **Produto de balança** de **Não** para **Sim**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações na base de dados do canal

1.  Vá para **Comércio e varejo** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
2.  Selecione a agenda de distribuição **1040**.
3.  Clique em **Executar agora** para sincronizar alterações no PDV.

Assim que os dados são sincronizados, quando um produto de balança é adicionado à transação de PDV, o PDV verifica a balança para obter o peso.

### <a name="signature-capture"></a>Assinatura

O dispositivo de captura de assinatura virtual solicita ao usuário que forneça uma assinatura no tapete de captura de assinatura virtual sempre que a proposta usada requerer uma assinatura. O usuário poderá aceitar a assinatura para exibi-la no PDV. O caixa poderá então aceitar a assinatura. A assinatura é então salva junto com a proposta e é sincronizada no back office junto com outros dados da transação.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Configurar uma proposta para exigir uma assinatura

1.  Vá para **Comércio e varejo** &gt; **Canais** &gt; **Lojas de varejo** &gt; **Todas as lojas de varejo**.
2.  Selecione a loja.
3.  Clique em **Editar**.
4.  Clique em **Configurar**, e então, na seção **Configurar**, clique em **Métodos de pagamento**.
5.  Clique em **Editar**.
6.  Selecione o método de pagamento que requer uma assinatura.
7.  Na seção **Geral**, em **Captura de assinatura**, defina a opção **Utilizar dispositivo de captura de assinatura** para **Sim**.
8.  No campo **Quantidade mínima para captura de assinatura**, insira a quantidade mínima que deve acionar a captura de assinatura.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar alterações na base de dados do canal

1.  Vá para **Comércio e varejo** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
2.  Selecione a agenda de distribuição **1070**.
3.  Clique em **Executar agora** para sincronizar alterações no PDV.

Assim que os dados forem sincronizados, quando uma proposta que requer assinatura é usada, e a quantia atinge o limite de assinatura, o PDV solicita uma assinatura no dispositivo de captura de assinatura virtual.

## <a name="additional-configuration"></a>Configurações adicionais
Você pode editar o arquivo de configurações do simulador periférico para melhor adaptá-lo aos cenários que deseja testar. Você pode encontrar o arquivo de configuração em C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. O arquivo de configuração define as unidades disponíveis para teste na balança, os tipos de cartões disponíveis para teste e os tipos de códigos de barras. Por exemplo, ao modificar os valores de texto no arquivo de configuração, você pode adicionar um novo tipo de cartão ou unidade de medida que pode ser selecionado no momento da execução. Os novos valores aparecerão depois que o aplicativo for reiniciado.

## <a name="troubleshooting"></a>Solução de problemas
As atividades do simulador periférico são registradas dentro do simulador periférico. Você pode encontrar o registro em C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. O simulador periférico também relata problemas ao registro de eventos do Windows, que pode ser acessado em **Registros de Aplicativos e Serviços** &gt; **Microsoft** &gt; **DynamicsAX**. Se as alterações feitas no perfil de hardware ou em outras áreas não estão evidentes ao utilizar o MPOS ou o simulador periférico, verifique os trabalhos do programador de distribuição que você utilizava para sincronizar dados à base de dados do canal. Se as alterações foram sincronizadas mas ainda não estão evidentes no PDV, reinicie o cliente PDV. As alterações nas gavetas de dinheiro configuradas não se tornam efetivas até que um novo turno seja criado. Portanto, se você fizer alterações nas gavetas de dinheiro, certifique-se de sempre fechar o turno existente para testar a nova configuração da gaveta de dinheiro. Eventualmente, se um driver do fabricante é instalado depois dos objetos de controle usuais da Monroe Consulting Services, o driver pode fazer com que os objetos de controle usuais parem de funcionar corretamente. Nesse caso, você deve reinstalar os objetos de controle usuais.

<a name="see-also"></a>Consulte também
--------

[Visão geral sobre os periféricos de varejo](retail-peripherals-overview.md)




