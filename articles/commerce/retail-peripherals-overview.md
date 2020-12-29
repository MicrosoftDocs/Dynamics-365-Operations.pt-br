---
title: Periféricos
description: Este tópico explica os conceitos relacionados aos periféricos do Commerce.
author: rubencdelgado
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice, RetailHardwareProfile
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dd2ce6b223c99d890691d5fdb9f93a5ceaf33a0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410309"
---
# <a name="peripherals"></a>Periféricos

[!include[banner](includes/banner.md)]

Este tópico explica os conceitos relacionados aos periféricos da loja. Descreve as várias formas que os periféricos podem ser conectados ao ponto de venda (PDV) e os componentes responsáveis por gerenciar a conexão com o PDV.

## <a name="concepts"></a>Conceitos

### <a name="pos-registers"></a>Terminais de PDV

Navegação: Clique em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Terminais**. O registro de ponto de venda (PDV) é uma entidade usada para definir as características de uma instância específica do PDV. Essas características incluem o perfil ou configuração de hardware para os periféricos que serão usados no registro, a loja em que o registro está mapeado, e a experiência visual para o usuário que se conecta ao registro.

### <a name="devices"></a>Dispositivos

Navegação: Clique em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Dispositivos**. Um dispositivo é uma entidade que representa uma instância física de um dispositivo que é mapeado para um registro de POS. Quando um dispositivo é criado, ele é mapeado para um registro de PDV. A entidade de dispositivo controla informações sobre quando uma registradora de POS é ativada, o tipo de cliente que está sendo usado e o pacote de aplicativo que foi implantado para um dispositivo específico. 

Os dispositivos podem ser mapeados nos seguintes tipos de aplicativo: Retail Modern POS, PDV de nuvem de varejo, Retail Modern POS – Windows Phone, Retail Modern POS – Android e Retail Modern POS – iOS.

### <a name="modern-pos"></a>POS moderno

O PDV moderno é o programa de PDV para Microsoft Windows. Pode ser implantado em sistemas operacionais Windows 10 (OSs).

### <a name="cloud-pos"></a>PDV em Nuvem

O PDV de nuvem é uma versão baseada em navegador do programa de PDV moderno que pode ser acessada em um navegador de Web.

### <a name="modern-pos-for-ios"></a>POS moderno para iOS

O PDV moderno para iOS é uma versão baseada em iOS do programa de PDV moderno que pode ser implantada em dispositivos iOS.

### <a name="modern-pos-for-android"></a>POS moderno para Android

O PDV moderno para Android é uma versão baseada em Android do programa de PDV moderno que pode ser implantada em dispositivos Android.

### <a name="pos-peripherals"></a>Periféricos de PDV

Os periféricos de PDV são dispositivos suportados explicitamente para funções de PDV. Esses periféricos normalmente são divididos em classes específicas. Para obter mais informações sobre essas classes, consulte a seção "Classes de dispositivo" deste tópico.

### <a name="hardware-station"></a>Hardware Station

Navegação: Clique em **Varejo e Comércio** &gt; **Canais** &gt; **Lojas** &gt; **Todas as lojas**. Selecione uma loja e clique na Guia Rápida **Estações de hardware**. A configuração **Estação de hardware** é uma configuração a nível de canal utilizada para definir instâncias onde a lógica de periférico será implantada. Esta configuração a nível de canal é usada para determinar as características da estação de hardware. Também é usada para listar as estações de hardware disponíveis para uma instância de PDV moderno em uma loja específica. A estação de hardware é criada nos programas de Modern POS para o Windows e Android. A estação de hardware também pode ser implantada independentemente como um programa autônomo do Microsoft Internet Information Services (IIS). Nesse caso, pode ser acessada pela rede.

### <a name="hardware-profile"></a>Perfil de hardware

Navegação: Clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**. O perfil de hardware é uma lista de dispositivos que são configurados para um registro de PDV ou estação de hardware. O perfil de hardware pode ser mapeado diretamente em um registro de PDV ou estação de hardware.

## <a name="devices-classes"></a>Classes de dispositivos
Os periféricos de PDV normalmente são divididos em classes. Esta seção descreve e dá uma visão geral dos dispositivos suportados pelo PDV moderno.

### <a name="printer"></a>Impressora

As impressoras incluem impressoras tradicionais de recibo de PDV e impressoras de página inteira. As impressoras são suportadas por meio da fixação e incorporação de objetos para Retail POS (OPOS) e interfaces de driver do Microsoft Windows. Até duas impressoras podem ser usadas ao mesmo tempo. Este recurso suporta cenários onde os recebimentos de cliente pague-e-leve são impressos em impressoras de recebimento, enquanto que as ordens de cliente, que têm mais informações, são impressas em uma impressora de página inteira. As impressoras de recebimento podem estar associadas diretamente a um computador via USB, conectadas à rede via Ethernet, ou conectadas via Bluetooth.

### <a name="scanner"></a>Scanner

Até duas impressoras de código de barras podem ser usadas ao mesmo tempo. Este recurso suporta cenários onde um scanner mais compatível com dispositivos é necessário para digitalizar itens grandes ou pesados, enquanto um scanner fixo inserido é usado para a maioria dos itens de dimensão padrão, para acelerar os tempos de checkout. Os scanners podem ser suportados pelo OPOS, plataforma universal do Windows (UWP) ou interfaces de teclado. O USB ou Bluetooth podem ser usados para conectar um scanner a um computador.

### <a name="msr"></a>LTM

Um leitor de tarja magnética (MSR) USB pode ser configurado usando drivers OPOS. Se desejar usar um MSR autônomo para transações de pagamento de transferência eletrônica de fundos (TEF), o MSR deve ser gerenciado por um conector de pagamento. Os MSRs autônomos podem ser usados para a entrada de fidelidade do cliente, o logon de funcionário, e entrada de vale-presente, independentemente do conector de pagamento.

### <a name="cash-drawer"></a>Gaveta de caixa

Duas gavetas de caixa podem ser suportadas pelo perfil de hardware. Este recurso permite que dois turnos ativos estejam disponíveis ao mesmo tempo por registradora. No caso de um turno compartilhado, ou uma caixa registradora usada por vários dispositivos móveis PDV ao mesmo tempo, apenas uma caixa registradora será permitida por perfil de hardware. As caixas registradores podem ser conectadas diretamente a um computador via USB, a uma rede, ou a uma impressora de recibos através de uma interface RJ12. Em alguns casos, as caixas registradoras também podem ser conectadas por meio de Bluetooth.

### <a name="line-display"></a>Display LCD de linhas

As exibições de linha são usadas para mostrar produtos, saldos da transação, e outras informações úteis ao cliente durante uma transação. A exibição de uma linha pode ser vinculada ao computador via USB usando drivers OPOS.

### <a name="signature-capture"></a>Assinatura

Os dispositivos de captura de assinatura podem ser vinculados diretamente a um computador via USB ou usando drivers OPOS. Quando a captura de assinatura for configurada, o cliente receberá uma solicitação para efetuar login no dispositivo. Depois que a assinatura for fornecida, ela é mostrada ao caixa para aceitação.

### <a name="scale"></a>Balança

As escalas podem ser conectadas ao computador via USP usando drivers OPOS. Quando um produto que está marcado como um produto "Ponderado" é adicionado a uma transação, o PDV lê o peso da escala, adiciona o produto à transação e usa a quantidade fornecida pela escala.

### <a name="pin-pad"></a>Teclado do PIN

Os teclados de número de identificação pessoal (PIN) são suportados no OPOS, mas devem ser gerenciados através de um conector de pagamento.

### <a name="secondary-display"></a>Exibição secundária

Quando uma exibição secundária for configurada, a exibição do Windows de número 2 será usada para mostrar informações básicas. A finalidade da exibição secundária é suportar uma extensão de fornecedor de software independente (ISV), pois fora do conjunto, a exibição secundária não pode ser configurada e apresenta conteúdo limitado.

### <a name="payment-device"></a>Dispositivo de pagamento

O suporte a dispositivos de pagamento foi implementado pelo conector de pagamento. Os dispositivos de pagamento podem realizar uma ou muitas das funções que outras classes de dispositivo fornecem. Por exemplo, um dispositivo de pagamento pode funcionar como um leitor de cartão/MSR, exibição de linha, dispositivo de captura de assinatura, ou teclado do PIN. O suporte a dispositivos de pagamento é implementado independentemente do suporte de dispositivo autônomo que é fornecido para outros dispositivos que estão inclusos no perfil de hardware.

## <a name="supported-interfaces"></a>Interfaces suportadas
### <a name="opos"></a>OPOS

Para ajudar a garantir que uma gama maior de dispositivos possa ser usada com o Commerce, o OLE para PDV padrão do setor é a plataforma de dispositivo periférico primária suportada. O OLE para PDV padrão foi produzido pela Federação Nacional do Varejo (NRF), que estabelece os protocolos de comunicação padrão da indústria para dispositivos periféricos. O OPOS é uma implementação amplamente adotada do OLE para PDV padrão. Foi desenvolvido em meados dos anos 90 e foi atualizado diversas vezes desde então. O OPOS fornece uma arquitetura de driver de dispositivo que permite a integração simples de hardware PDV com sistemas baseados em Windows. O OPOS controla a comunicação entre o hardware compatível e o software PDV. Um controle OPOS consiste em duas partes:

-   **Objeto de controle** – O objeto de controle para uma classe de dispositivo (como as exibições de linha) fornece a interface para o programa de software. A Monroe Serviços de Consultoria ([www.monroecs.com](http://www.monroecs.com/)) fornece um conjunto padronizado de objetos de controle OPOS que são conhecidos como objetos de controle (CCOs). Os CCOs são usados para testar o componente de PDV do Commerce. Portanto, o teste ajuda a garantir que, se o Commerce oferecer suporte a uma classe de dispositivo através do OPOS, muitos tipos de dispositivo poderão ser aceitos, desde que o fabricante forneça um objeto de serviço que seja desenvolvido para OPOS. Você não precisa explicitamente testar cada tipo do dispositivo.
-   **Objeto de serviço** – O objeto de serviço fornece comunicação entre o objeto de controle (CCO) e o dispositivo. Normalmente, o objeto de serviço para um dispositivo é fornecido pelo fabricante do dispositivo. Entretanto, em alguns casos, pode ser necessário baixar o objeto de serviço do site do fabricante. Por exemplo, um objeto mais recente de serviço pode estar disponível. Para localizar o endereço do site do fabricante, consulte a documentação do hardware.

[![Objeto de controle e objeto de serviço](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) O suporte à implementação de OPOS do OLE para PDV ajuda a garantir que, se os fabricantes de dispositivos e publicadores de PDV implementarem o padrão corretamente, os sistemas de PDV e dispositivos suportados podem trabalhar juntos, mesmo que não tenham sido testados anteriormente. 

> [!NOTE]
> O suporte do OPOS não garante suporte para todos os dispositivos com drivers OPOS. O Commerce deve primeiro oferecer suporte a esse tipo ou classe de dispositivo através do OPOS. Além disso, os objetos de serviço nem sempre podem estar atualizados com a versão mais recente dos CCOs. Você também deve estar ciente de que, em geral, a qualidade dos objetos de serviço é diferente.

### <a name="windows"></a>Windows

A impressão de recibo no PDV é otimizada para OPOS. O OPOS tende a ser muito mais rápido que a impressão com Windows. Portanto, é recomendável usar o OPOS, especialmente em ambientes onde recibos de 40 colunas são impressos e os tempos de transação devem ser curtos. Para a maioria de dispositivos, você usará controles OPOS. Entretanto, algumas impressoras de recibo OPOS também oferece suporte a drivers do Windows. Usando um driver do Windows, você pode acessar as fontes mais recentes e vincular uma impressora para várias registradoras. Contudo, há inconvenientes em usar os drivers do Windows. Veja aqui alguns exemplos desses inconvenientes:

-   Quando os drivers do Windows são usados, imagens são renderizadas antes que a impressão ocorra. Portanto, a impressão tende a ser mais lenta do que em impressoras que utilizam controles OPOS.
-   Os dispositivos conectados através da impressora ("encadeado") podem não funcionar corretamente quando os drivers do Windows forem utilizados. Por exemplo, a caixa registradora pode não abrir, a impressora de guia pode não escrever como você espera.
-   O OPOS também oferece suporte a um conjunto de variáveis mais amplo que são específicas para as impressoras de recibo, como corte de papéis ou impressão de guias.
-   As impressoras do Windows não oferecem suporte por meio da estação de hardware IIS. 

Se os controles OPOS estiverem disponíveis para a impressora do Windows que você está usando, a impressora ainda deverá funcionar corretamente com o Commerce.

### <a name="universal-windows-platform"></a>Plataforma de universal do Windows

A UWP, em caso de periféricos, é relacionada ao suporte do Windows para dispositivos Plug and Play. Quando um dispositivo Plug and Play é conectado a uma versão do Windows que oferece suporte a esse tipo de dispositivo, nenhum driver é necessário para que o dispositivo seja usado conforme pretendido. Por exemplo, se o Windows detectar um dispositivo de alto-falante Bluetooth, o sistema operacional sabe que o dispositivo tem o tipo de classe **Alto-falante**. Portanto, ele gerencia esse dispositivo como um alto-falante. Nenhuma configuração adicional é necessária. No caso de dispositivos PDV, vários dispositivos USB podem ser conectados, e o Windows irá reconhecê-los dispositivos (HIDs) de interface humana. Entretanto, ele não consegue determinar os recursos que o dispositivo fornece, pois o dispositivo não especifica a classe ou tipo do dispositivo. No Windows 10, classes de dispositivo para scanner de código de barras e MSRs foram adicionados. Portanto, se um dispositivo se declarar para o Windows 10 como um dispositivo de uma dessas classes, o Windows escutará eventos do dispositivo em horários apropriados. O PDV moderno oferece suporte a MSRs e scanners UWP. Portanto, quando estiver pronto para entrada de um desses dispositivos, e um dispositivo que pertence a uma dessas classes é conectado, o dispositivo pode ser usado. Por exemplo, se um scanner de código de barras UWP for conectado a um computador com Windows 10, e o logon de código de barras estiver configurado para o PDV moderno, o scanner de código de barras ficará ativo na tela de logon. Nenhuma configuração adicional é necessária. As classes adicionais de dispositivos UWP de ponto de serviço estão sendo adicionadas ao Windows. Essas classes incluem classes para caixas registradoras e impressoras de recibo. O suporte para essas novas classes de dispositivo no PDV moderno está pendente.

### <a name="keyboard-wedge"></a>Leitor de cartão de crédito do teclado

Os leitores de cartão de crédito do teclado enviam dados para o computador como se os dados tivessem sido digitados em um teclado. Portanto, por padrão, o campo que fica ativo no PDV receberá os dados digitalizados ou lidos. Em alguns casos, este comportamento pode fazer com que o tipo errado de dado seja digitalizado no campo errado. Por exemplo, um código de barras pode ser digitalizado em um campo que foi criado para a entrada de dados de cartão de crédito. Em muitos casos, há uma lógica no PDV que determina se os dados que são digitalizados ou lidos são um código de barras ou faixa de cartão. Portanto, os dados são controlados corretamente. Entretanto, quando dispositivos são configurados como OPOS em vez de leitores de cartão de crédito do teclado, há mais controle sobre a forma como os dados desses dispositivos podem ser consumidos, pois o dispositivo de origem dos dados é mais "conhecido". Por exemplo, os dados de um scanner de código de barras são reconhecidos automaticamente como um código de barras, e o registro associado no banco de dados é encontrado com mais facilidade e rapidez do que se uma pesquisa de cadeia de caracteres genérica fosse utilizada, como no caso dos leitores de cartão de crédito de teclado.

### <a name="native-printer"></a>Impressora nativa

As impressoras nativas (ou "dispositivo", uma vez que o tipo é nomeado no perfil de hardware) podem ser configuradas para que solicitam ao usuário que selecione uma impressora que está configurada para o computador. Quando uma impressora do tipo **Dispositivo** é configurada, se o PDV moderno encontrar um comando de impressão, é solicitado ao usuário que selecione uma impressora em uma lista. Esse comportamento difere do comportamento dos drivers do Windows, pois o tipo de impressora do **Windows** no perfil de hardware não mostra uma lista de impressoras. Em vez disso, ele exige que uma impressora nomeada seja fornecida no campo **Nome do dispositivo**.

### <a name="network"></a>Rede

As caixas registradoras endereçáveis por rede, impressoras de recibo e terminais de pagamento podem ser usados em uma rede, seja diretamente através da estação de hardware de Comunicação Interprocesso (IPC) integrada no PDV moderno para Windows ou através da estação de hardware IIS para outros clientes de PDV moderno.

## <a name="hardware-station-deployment-options"></a>Opções de implantação de estação de hardware

### <a name="dedicated"></a>Dedicada

Os clientes do Modern POS para Windows e Android incluem estações de hardware **Dedicadas** ou integradas. Esses clientes podem se comunicar diretamente com periféricos usando a lógica de negócios integrada aos aplicativos. O aplicativo Android oferece suporte somente a dispositivos de rede. Para obter mais informações sobre suporte a periféricos para o Android, acesse o artigo [Configurar aplicativo POS Hybrid no Android e iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp).

Para usar a estação de hardware dedicada, atribua um perfil de hardware a um registro que usará o Modern POS para Windows ou aplicativo Android. Em seguida, crie uma estação de hardware do tipo **Dedicada** para a loja onde a registradora será utilizada. Inicie o Modern POS no modo sem gaveta e use a operação **Gerenciar estações de hardware** para acionar os recursos da estação de hardware, a estação de hardware dedicada estará ativa por padrão. Em seguida, faça logoff do Modern POS e entre novamente. Depois, abra um turno e os periféricos configurados no perfil de hardware poderão ser usados. 

### <a name="shared"></a>Compartilhada 

Às vezes também referida como a estação de hardware "IIS", "IIS" indica que o aplicativo de PDV se conecta à estação de hardware via Serviços de Informações da Internet da Microsoft. O aplicativo PDV se conecta à estação de hardware IIS através dos serviços de web que estão sendo executados em um computador onde os dispositivos estão conectados. Quando a estação de hardware compartilhada é usada, os periféricos que estiverem conectados a uma estação de hardware podem ser usados por qualquer registradora PDV que estiver na mesma rede que a estação de hardware IIS. Embora apenas o Modern POS para Windows e Android incluam suporte integrado para periféricos, todos os demais aplicativos de Modern POS devem usar a estação de hardware IIS para se comunicar com os periféricos de PDV que estão configurados no perfil de hardware. Portanto, cada instância da estação de hardware IIS requer um computador que execute o serviço e o aplicativo de Web que se comunica com os dispositivos. 

A estação de hardware compartilhada pode ser usada para permitir que vários clientes do ponto de venda compartilhem periféricos ou pode ser usada para gerenciar um conjunto comprometido ou periféricos para um único ponto de venda. 

Quando uma estação de hardware é usada para oferecer suporte a periféricos entre vários clientes do PDV, somente as caixas registradoras, as impressoras de recibo e os terminais de pagamento devem ser usados. Você não pode conectar diretamente scanners de código de barras autônomos, MSRs, exibições de linha, escalas ou outros dispositivos. Caso contrário, conflitos ocorrerão quando vários dispositivos PDV tentam reivindicar simultaneamente os periféricos. Veja como os conflitos são gerenciados para os dispositivos com suporte:

-   **Caixa registradora** – A caixa registradora é aberta através de um evento que é enviado ao dispositivo. O único problema que pode ocorrer quando a caixa registradora é chamada ocorre se ela já estiver aberta. No caso de estações de hardware compartilhadas, a caixa registradora deve ser definida como **Compartilhada** no perfil de hardware. Essa configuração impede que o PDV verifique se a caixa registradora já está aberta ao enviar comandos de abertura.
-   **Impressora de recibo** – Se dois comandos de impressão de recibo forem enviados para a estação de hardware ao mesmo tempo, um dos comandos poderá ser perdido dependendo do dispositivo. Alguns dispositivos têm memória interna ou agrupamento que pode impedir esse problema. Se um comando de impressão não tiver êxito, o caixa receberá uma mensagem de erro e poderá tentar novamente o comando de impressão no PDV.
-   **Terminal de pagamento** – Se um caixa tentar realizar uma transação em um terminal de pagamento que já está sendo utilizado, uma mensagem notificará o caixa de que o terminal está sendo usado e pedirá ao caixa que tente novamente mais tarde. Geralmente, os caixas podem consultar um terminal que já está sendo usado e aguardarão até que outra transação seja concluída antes que tentem novamente.

A validação é planejada para uma versão futura, para detectar se dispositivos sem suporte estão configurados para um perfil de hardware que está mapeado para uma estação compartilhada de hardware. Se qualquer dispositivo sem suporte for detectado, o usuário receberá uma mensagem que indica que os dispositivos não são aceitos para estações compartilhadas de hardware. No caso de estações compartilhadas de hardware, a opção **Selecionar após pagamento** é definida para **Sim** em nível de registro. Em seguida, é solicitado ao usuário do PDV que selecione uma estação de hardware quando uma proposta for selecionada para uma transação no PDV. Quando a estação de hardware é selecionada somente no momento de proposta, a seleção de estação de hardware é adicionada diretamente ao fluxo de trabalho do PDV para os cenários móveis. Como um benefício adicional, a exibição de linha no terminal de pagamento não é utilizada para cenários compartilhados. Se o terminal de pagamento for usado como exibição de linha, outros usuários podem ser impedidos de usar esse terminal até que a transação esteja concluída. Em cenários móveis, as linhas podem ser adicionadas em uma transação durante um período mais longo. Portanto, a opção **Selecionar após proposta** é necessária para garantir uma disponibilidade ideal do dispositivo.

### <a name="network-peripherals"></a>Periféricos de rede

A designação de rede para dispositivos no perfil de hardware permite que caixas registradoras, impressoras de recibo e terminais de pagamento sejam conectados através de uma conexão de rede.

#### <a name="modern-pos-for-windows"></a>PDV moderno para Windows

Você pode especificar o endereço IP de periféricos de rede em dois locais. Se o cliente do PDV moderno do Windows estiver usando um conjunto único de periféricos de rede, você deverá definir os endereços IP para esses dispositivos usando a opção **Configuração de IP** no painel de ação para o registro em si. No caso de dispositivos de rede que serão compartilhados entre registradoras de PDV, um perfil de hardware que possui dispositivos de rede atribuídos a ele poderá ser mapeado diretamente a uma estação de hardware compartilhada. Para atribuir endereços IP, selecione a estação de hardware na página **Lojas**, e use a opção **Configuração de IP** na seção **Estações de hardware** para especificar os dispositivos de rede que estão atribuídos à estação de hardware. Para as estações de hardware que possuem somente dispositivos de rede, você não precisa implantar a estação de hardware. Nesse caso, a estação de hardware é necessária somente para agrupar de forma conceitual os dispositivos endereçáveis de rede de acordo com sua localização na loja.

#### <a name="cloud-pos-and-modern-pos-for-ios"></a>PDV em Nuvem e Modern POS para iOS

A lógica que controla os periféricos endereçáveis por rede e conectados fisicamente está contida na estação de hardware. Portanto, para todos os clientes PDV, exceto o Modern POS para Windows e Android, uma estação de hardware IIS deve estar implantada e ativa para permitir que o PDV se comunique com os periféricos, independentemente dos periféricos estarem conectados fisicamente à uma estação de hardware ou endereçados pela rede.

## <a name="setup-and-configuration"></a>Instalação e configuração
### <a name="hardware-station-installation"></a>Instalação da estação de hardware

Para obter informações, consulte [Configurar e instalar a estação de hardware](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Instalação e configuração do PDV moderno para Windows

Para obter informações, consulte [Configurar, instalar e ativar o Modern POS (MPOS)](retail-modern-pos-device-activation.md).

### <a name="modern-pos-for-android-and-ios-setup-and-configuration"></a>Instalação e configuração do Modern POS para Android e iOS

Para obter informações, consulte [Configurar o aplicativo POS Hybrid no Android e iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp).

### <a name="opos-device-setup-and-configuration"></a>Instalação e configuração do dispositivo OPOS

Para obter mais informações sobre os componentes do OPOS, consulte a seção "Interfaces suportadas" deste documento. Normalmente, os drivers OPOS são fornecidos pelo fabricante do dispositivo. Quando um driver de dispositivo OPOS é instalado, ele adiciona uma chave ao registro do Windows em um dos seguintes locais:

-   **Sistema de 32 bits:** HKEY\_LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS
-   **Sistema de 64 bits:** HKEY\_LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

Dentro no local de registro ServiceOPOS, os dispositivos configurados são organizados de acordo com a classe de dispositivo OPOS. Vários drivers de dispositivo são salvos.

## <a name="supported-scenarios-by-hardware-station-type"></a>Cenários suportados pelo tipo de estação de hardware
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Suporte do cliente - Estação de hardware IPC vs. estação de hardware IIS

A tabela a seguir mostra as topologias e cenários de implantação suportados.

| Cliente      | Estação de hardware IPC | Estação de hardware IIS |
|-------------|----------------------|----------------------|
| App do Windows | Sim                  | Sim                  |
| PDV em Nuvem   | Não                   | Sim                  |
| Android     | Sim                  | Sim                  |
| iOS         | Não                   | Sim                  |

### <a name="network-peripherals"></a>Periféricos de rede

Os periféricos de rede podem ser suportados diretamente através da estação de hardware integrada no Modern POS para aplicativos do Windows e Android. Para todos os outros clientes, você deve implantar uma estação de hardware IIS.

| Cliente      | Estação de hardware IPC | Estação de hardware IIS |
|-------------|----------------------|----------------------|
| App do Windows | Sim                  | Sim                  |
| PDV em Nuvem   | Não                   | Sim                  |
| Android     | Sim                  | Sim                  |
| iOS         | Não                   | Sim                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Tipos de dispositivo suportados pelo tipo de estação de hardware
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>PDV moderno para Windows com uma estação de hardware IPC (integrada)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de dispositivo suportada</th>
<th>Interfaces suportadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impressora</td>
<td><ul>
<li>OPOS</li>
<li>Driver do Windows</li>
<li>Dispositivo</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="even">
<td>Impressora 2</td>
<td><ul>
<li>OPOS</li>
<li>Driver do Windows</li>
<li>Dispositivo</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="odd">
<td>Display LCD de linhas</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Exibição dual</td>
<td>Driver do Windows</td>
</tr>
<tr class="odd">
<td>LTM</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nenhuma configuração é necessária.)</li>
<li>Leitor de cartão no teclado (nenhuma configuração é necessária.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Sacador</td>
<td><ul>
<li>OPOS</li>
<li>Rede </br><strong>Observação:</strong> Somente uma caixa registradora poderá ser configurada se <strong>Usar turno compartilhado</strong> estiver configurado na caixa registradora.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Gaveta 2</td>
<td><ul>
<li>OPOS</li>
<li>Rede </br><strong>Observação:</strong> Somente uma caixa registradora poderá ser configurada se <strong>Usar turno compartilhado</strong> estiver configurado na caixa registradora.</li>
</ul></td>
</tr>
<tr class="even">
<td>Scanner</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nenhuma configuração é necessária.)</li>
<li>Leitor de cartão no teclado (nenhuma configuração é necessária.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanner 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nenhuma configuração é necessária.)</li>
<li>Leitor de cartão no teclado (nenhuma configuração é necessária.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Balança</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Teclado do PIN</td>
<td>OPOS (o suporte é fornecido através da personalização do conector de pagamento.)</td>
</tr>
<tr class="even">
<td>Assinatura</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Terminal de pagamento</td>
<td><ul>
<li>Suporte personalizado de dispositivo</li>
<li>Rede (para mais informações, consulte a documentação do conector de pagamento.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Todos os clientes de Modern POS que possuem uma estação de hardware IIS "Compartilhada" comprometida

> [!NOTE]
> Quando a estação de hardware IIS é "comprometida", há uma relação de um para um entre o cliente do PDV e a estação de hardware.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de dispositivo suportada</th>
<th>Interfaces suportadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impressora</td>
<td><ul>
<li>OPOS</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="even">
<td>Impressora 2</td>
<td><ul>
<li>OPOS</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="odd">
<td>Display LCD de linhas</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>LTM</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Sacador</td>
<td><ul>
<li>OPOS</li>
<li>Rede </br><strong>Observação:</strong> Somente uma caixa registradora por perfil de hardware poderá ser configurada se <strong>Usar turno compartilhado</strong> estiver configurado na caixa registradora.</li>
</ul></td>
</tr>
<tr class="even">
<td>Gaveta 2</td>
<td><ul>
<li>OPOS</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanner</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Scanner 2</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Balança</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Teclado do PIN</td>
<td>OPOS (o suporte é fornecido através da personalização do conector de pagamento.)</td>
</tr>
<tr class="odd">
<td>Sig. captura</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Terminal de pagamento</td>
<td><ul>
<li>Suporte personalizado de dispositivo</li>
<li>Rede (para mais informações, consulte a documentação do conector de pagamento.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-shared-an-iis-hardware-station"></a>Todos os clientes de Modern POS compartilhavam uma estação de hardware IIS

> [!NOTE]
> Quando a estação de hardware IIS é "compartilhada", vários dispositivos podem usar a estação de hardware ao mesmo tempo. Para esse cenário, você deve usar apenas os dispositivos listados na tabela. Se você tentar compartilhar dispositivos que não estão listados aqui, como scanners de código de barras e MSRs, erros ocorrerão quando vários dispositivos tentarem reivindicar o mesmo periférico. Futuramente, tal configuração será impedida explicitamente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de dispositivo suportada</th>
<th>Interfaces suportadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impressora</td>
<td><ul>
<li>OPOS</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="even">
<td>Impressora 2</td>
<td><ul>
<li>OPOS</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sacador</td>
<td><ul>
<li>OPOS</li>
<li>Rede </br><strong>Observação:</strong> Somente uma caixa registradora por perfil de hardware poderá ser configurada se <strong>Usar turno compartilhado</strong> estiver configurado na caixa registradora.</li>
</ul></td>
</tr>
<tr class="even">
<td>Gaveta 2</td>
<td><ul>
<li>OPOS</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="odd">
<td>Terminal de pagamento</td>
<td><ul>
<li>Suporte personalizado de dispositivo</li>
<li>Rede (para mais informações, consulte a documentação do conector de pagamento.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configuração para cenários suportados
Para obter mais informações sobre como criar perfis de hardware, consulte [Definir e manter clientes de canal, incluindo registros e estações de hardware](define-maintain-channel-clients-registers-hw-stations.md). 

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>PDV moderno para Windows com uma estação de hardware IPC (integrada)

Esta configuração é a configuração mais típica para as registradoras PDV fixas tradicionais. Para esse cenário, as informações de perfil de hardware são mapeadas diretamente na registradora. O número do terminal de TEF também pode ser configurado na registradora. Para fazer essa configuração, siga essas etapas.

1.  Crie um perfil de hardware onde todos os periféricos necessários são configurados.
2.  Mapeie o perfil de hardware na registradora de PDV.
3.  Crie uma estação de hardware do tipo **Dedicada** para a loja onde o terminal de PDV será utilizado. Uma descrição é opcional. 

    > [!NOTE]
    > Você não precisa definir outras propriedades na estação de hardware. Todas as outras informações necessárias, como perfil de hardware, serão provenientes da registradora.

4.  Clique em **Retail e Commerce** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição**.
5.  Selecione a agenda de distribuição **1090** para sincronizar o novo perfil de hardware com a loja. Clique em **Executar agora** para sincronizar as alterações do PDV.
6.  Selecione a agenda de distribuição **1040** para sincronizar a nova estação de hardware com a loja. Clique em **Executar agora** para sincronizar as alterações do PDV.
7.  Instale e ative o PDV moderno para Windows.
8.  Inicie o PDV moderno para Windows, e comece a usar os dispositivos periféricos conectados.

### <a name="modern-pos-for-android-with-an-ipc-built-in-hardware-station"></a>Modern POS para Android com uma estação de hardware IPC (integrada)

**Novo para 10.0.8** – impressoras de rede Epson e caixas registradoras conectadas a elas via porta DK agora oferecem suporte para Modern POS para o aplicativo Android. Para obter detalhes, acesse o artigo [Configurar o aplicativo POS Hybrid no Android e iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp).

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Todos os clientes de Modern POS que possuem uma estação de hardware IIS compartilhada comprometida

Essa configuração pode ser usada para todos os clientes de PDV moderno que possuem uma estação de hardware usada exclusivamente por uma registradora de PDV. Para fazer essa configuração, siga essas etapas.

1.  Crie um perfil de hardware onde todos os periféricos necessários são configurados.
2.  Crie uma estação de hardware do tipo **Dedicada** para a loja onde o terminal de PDV será utilizado.
3.  Na estação dedicada de hardware, defina as seguintes propriedades:
    -   **Nome do host** – O nome do computador host onde a estação de hardware será executada. 
    
        > [!NOTE]
        > O PDV de nuvem pode resolver o **localhost** para determinar o computador local onde o PDV de Nuvem está sendo executado. No entanto, o certificado necessário para emparelhar o PDV de nuvem com a estação de hardware também deve ter "Localhost" como nome de computador. Para evitar problemas, recomendamos que você liste uma instância de cada estação dedicada de hardware para a loja, conforme necessário. Para cada estação de hardware, o nome do host deve ser o nome do computador específico onde a estação de hardware será implantada.
    
    -   **Porta** – A porta a ser usada para a estação de hardware se comunicar com o cliente de PDV moderno.
    -   **Perfil de hardware** – Se o perfil de hardware não for fornecido na estação de hardware, o perfil de hardware atribuído à registradora será usado.
    -   **Número de PDV da TEF** – A ID do terminal de TEF a ser usado quando autorizações de TEF forem enviadas. Essa ID é fornecida pelo processador de cartão de crédito.
    -   **Nome do pacote** – O pacote de estação de hardware a ser usado quando a estação de hardware é implantada.

4.  Clique em **Retail e Commerce** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição**.
5.  Selecione a agenda de distribuição **1090** para sincronizar o novo perfil de hardware com a loja. Clique em **Executar agora** para sincronizar as alterações do PDV.
6.  Selecione a agenda de distribuição **1040** para sincronizar a nova estação de hardware com a loja. Clique em **Executar agora** para sincronizar as alterações do PDV.
7.  Instale a estação de hardware. Para mais informações sobre como instalar a estação de hardware, consulte [Configurar e instalar o Retail hardware station](retail-hardware-station-configuration-installation.md).
8.  Instale e ative o PDV moderno. Para obter mais informações sobre como instalar o Modern POS, consulte [Configurar, instalar e ativar o Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md).
9.  Entre no PDV moderno e selecione **Realizar operações que não são de gaveta**.
10. Inicie a operação **Gerenciar estações de hardware**.
11. Clique em **Gerenciar**.
12. Na página de gerenciamento da estação de hardware, defina a opção para ativar a estação de hardware.
13. Selecione a estação de hardware a ser usada e, em seguida, clique em **Emparelhar**.
14. Após a estação de hardware ser emparelhada, clique em **Fechar**.
15. Na página de seleção da estação de hardware, clique na estação de hardware selecionada recentemente para ativá-la.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Todos os clientes de PDV modernos que possuem uma estação de hardware IIS compartilhada

Essa configuração pode ser usada para todos os clientes de PDV moderno que compartilham estações de hardware com outros dispositivos. Para fazer essa configuração, siga essas etapas.

1.  Crie um perfil de hardware onde os periféricos necessários são configurados.
2.  Crie uma estação de hardware do tipo **Compartilhada** para a loja onde o terminal de PDV será utilizado.
3.  Na estação compartilhada de hardware, defina as seguintes propriedades:
    -   **Nome do host** – O nome do computador host onde a estação de hardware será executada.
    -   **Descrição** – Texto que ajudará a identificar a estação de hardware, como **Devoluções** ou **Vitrine da loja**.
    -   **Porta** – A porta a ser usada para a estação de hardware se comunicar com o cliente de PDV moderno.
    -   **Perfil de hardware** – Para as estações de hardware compartilhadas, cada estação de hardware deve ter um perfil de hardware. Os perfis de hardware podem ser compartilhados entre as estações de hardware, mas devem ser mapeados em cada estação de hardware. Além disso, recomendamos que você use turnos compartilhados quando vários dispositivos usarem a mesma estação de hardware compartilhada. Para configurar um turno compartilhado, clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**. Para cada perfil de hardware compartilhado, selecione a caixa registradora, e defina a opção **Gaveta de turno compartilhado** para **Sim**.
    -   **Número de PDV da TEF** – A ID do terminal de TEF a ser usado quando autorizações de TEF forem enviadas. Essa ID é fornecida pelo processador de cartão de crédito.
    -   **Nome do pacote** – O pacote de estação de hardware a ser usado quando a estação de hardware é implantada.

4.  Repita as etapas 2 e 3 para cada estação de hardware adicional necessária na loja.
5.  Clique em **Retail e Commerce** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição**.
6.  Selecione a agenda de distribuição **1090** para sincronizar o novo perfil de hardware com a loja. Clique em **Executar agora** para sincronizar as alterações do PDV.
7.  Selecione a agenda de distribuição **1040** para sincronizar a nova estação de hardware com a loja. Clique em **Executar agora** para sincronizar as alterações do PDV.
8.  Instale a estação de hardware em cada computador host que é configurado nas etapas 2 e 3. Para mais informações sobre como instalar a estação de hardware, consulte [Configurar e instalar o Retail hardware station](retail-hardware-station-configuration-installation.md).
9.  Instale e ative o PDV moderno. Para obter mais informações sobre como instalar o Modern POS, consulte [Configurar, instalar e ativar o Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md).
10. Entre no PDV moderno e selecione **Realizar operações que não são de gaveta**.
11. Inicie a operação **Gerenciar estações de hardware**.

12. Clique em **Gerenciar**.
13. Na página de gerenciamento da estação de hardware, defina a opção para ativar a estação de hardware.
14. Selecione a estação de hardware a ser usada e, em seguida, clique em **Emparelhar**.
15. Repita a etapa 14 para cada estação de hardware que o PDV moderno usará.
16. Após todas as estações de hardware necessárias serem emparelhadas, clique em **Fechar**.
17. Na página de seleção da estação de hardware, clique na estação de hardware selecionada recentemente para ativá-la. 

> [!NOTE]
> Se dispositivos usarem frequentemente diferentes estações de hardware, é recomendável configurar o PDV moderno para solicitar aos caixas que selecionem uma estação de hardware quando começarem o processo de meio de pagamento. Clique em **Varejo e Comércio** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **Registros**. Selecione a registradora e, em seguida, defina a opção **Selecionar após proposta** para **Sim**. Use a agenda de distribuição **1090** para sincronizar alterações no banco de dados do canal.

## <a name="extensibility"></a>Extensibilidade
Para obter informações sobre cenários de extensibilidade da estação de hardware, consulte [Extensibilidade da estação de hardware](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Segurança
De acordo com os padrões de segurança atuais, as seguintes configurações devem ser usadas em um ambiente de produção: 

### <a name="hardware-station-installer"></a>Instalador da estação de hardware
O instalador da estação de hardware fará automaticamente essas edições de registro como parte da instalação no autoatendimento.
 
-   O SSL (Secure Sockets Layer) deve ser desabilitado.
-   Somente o TLS (Transport Layer Security) versão 1.2 (ou versão mais atual) deve ser habilitado e usado. 

### <a name="ssl-and-tls"></a>SSL e TLS
Por padrão, o SSL e todas as versões do TLS, exceto TLS 1.2, estão desabilitados. Para editar ou habilitar esses valores, siga estas etapas:
    1.  Pressione a tecla de logotipo do Windows+R para abrir uma janela de **Execução**.
    2.  No campo **Abrir**, digite **Regedit** e, em seguida, clique em **OK**.
    3.  Se uma caixa de mensagem **Controle de conta de usuário** for exibida, clique em **Sim**.
    4.  Na janela do **Editor de registro**, navegue até **HKEY\_LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. As seguintes chaves foram inseridas automaticamente para permitir somente o TLS 1.2:
        -   TLS 1.2Server:Enabled=1
        -   TLS 1.2Server:DisabledByDefault=0
        -   TLS 1.2Client:Enabled=1
        -   TLS 1.2Client:DisabledByDefault=0
        -   TLS 1.1Server:Enabled=0
        -   TLS 1.1Client:Enabled=0
        -   TLS 1.0Server:Enabled=0
        -   TLS 1.0Client:Enabled=0
        -   SSL 3.0Server:Enabled=0
        -   SSL 3.0Client:Enabled=0
        -   SSL 2.0Server:Enabled=0
        -   SSL 2.0Client:Enabled=0
-   Nenhuma porta de rede adicional deve ser aberta, a menos que seja necessário por motivos específicos e conhecidos.
-   O compartilhamento de recurso entre origens deve ser desabilitado e deve especificar as origens permitidas que são aceitas.
-   Somente as autoridades de certificação de confiança podem ser usadas para obter os certificados que serão usados nos computadores que executam a estação de hardware.

> [!NOTE]
> É muito importante que você examine as diretrizes de segurança para os requisitos de IIS e PCI (Payment Card Industry).

## <a name="peripheral-simulator"></a>Simulador periférico
Para obter informações, consulte [Simulador de periféricos para o Commerce](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsoft-tested-peripheral-devices"></a>Dispositivos periféricos testados pela Microsoft
### <a name="ipc-built-in-hardware-station"></a>Estação de hardware IPC (integrada)

Estes periféricos foram testados usando a estação de hardware IPC que é integrada no PDV moderno para Windows.

#### <a name="printer"></a>Impressora

| Fabricante | Modelo    | Interface | Comentários                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | OPOS      |                         |
| Epson        | TM-T88V  | OPOS      |                         |
| Epson        | TM-T88   | Personalizado    | Conectado via rede   |
| Star         | TSP650II | Personalizado    | Conectado via rede   |
| Star         | mPOP     | OPOS      | Conectado via Bluetooth |
| HP           | F7M67AA  | OPOS      | Porta USB             |

#### <a name="bar-code-scanner"></a>Scanner de código de barras

| Fabricante  | Modelo         | Interface | Comentários |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Símbolo        | LS2208        | OPOS      |          |
| HP Integrated | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Teclado do PIN

| Fabricante | Modelo  | Interface | Comentários                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Requer personalização do conector de pagamento |

#### <a name="payment-terminal"></a>Terminal de pagamento

| Fabricante | Modelo | Interface | Comentários                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizado    | Requer personalização do conector de pagamento                                |
| VeriFone     | MX925 | Personalizado    | Requer personalização do conector de pagamento; conectado via rede e USB |
| VeriFone     | MX915 | Personalizado    | Requer personalização do conector de pagamento; conectado via rede e USB |

#### <a name="cash-drawer"></a>Gaveta de caixa

| Fabricante | Modelo     | Interface | Comentários                |
|--------------|-----------|-----------|-------------------------|
| Star         | mPOP      | OPOS      | Conectado via Bluetooth |
| APG          | Atwood    | Personalizado    | Conectado via rede   |
| Star         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |
| Epson        |           | Personalizado    | Conectado à impressora de rede Epson via porta DK |

#### <a name="line-display"></a>Display LCD de linhas

| Fabricante  | Modelo   | Interface | Comentários |
|---------------|---------|-----------|----------|
| HP integrated | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Assinatura

| Fabricante | Modelo  | Interface | Comentários |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Balança

| Fabricante | Modelo         | Interface | Comentários |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>LTM

| Fabricante | Modelo       | Interface | Comentários |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Estação de hardware IIS dedicada

Os periféricos a seguir foram estados usando uma estação de hardware IIS dedicada (não compartilhada), junto com o PDV moderno para Windows e PDV de nuvem.

#### <a name="printer"></a>Impressora

| Fabricante | Modelo    | Interface | Comentários                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Epson        | TM-T88V  | Personalizado    | Conectado via rede     |
| Star         | TSP650II | Personalizado    | Conectado via rede     |
| HP           | F7M67AA  | OPOS      | Powered USB               |

#### <a name="bar-code-scanner"></a>Scanner de código de barras

| Fabricante  | Modelo   | Interface | Comentários |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Símbolo        | LS2208  | OPOS      |          |
| HP Integrated | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Teclado do PIN

| Fabricante | Modelo  | Interface | Comentários                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Requer personalização do conector de pagamento |

#### <a name="payment-terminal"></a>Terminal de pagamento

| Fabricante | Modelo | Interface | Comentários                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizado    | Requer personalização do conector de pagamento                                |
| VeriFone     | MX925 | Personalizado    | Requer personalização do conector de pagamento; conectado via rede e USB |
| VeriFone     | MX915 | Personalizado    | Requer personalização do conector de pagamento; conectado via rede e USB |

#### <a name="cash-drawer"></a>Gaveta de caixa

| Fabricante | Modelo     | Interface | Comentários              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizado    | Conectado via rede |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |
| Epson        |           | Personalizado    | Conectado à impressora de rede Epson via porta DK |

#### <a name="line-display"></a>Display LCD de linhas

| Fabricante  | Modelo   | Interface | Comentários |
|---------------|---------|-----------|----------|
| HP integrated | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Assinatura

| Fabricante | Modelo  | Interface | Comentários |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Balança

| Fabricante | Modelo         | Interface | Comentários |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>LTM

| Fabricante | Modelo       | Interface | Comentários |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Estação de hardware IIS compartilhada

Os periféricos a seguir foram estados usando uma estação de hardware IIS compartilhada, junto com o PDV moderno para Windows e PDV de nuvem. 

> [!NOTE]
> Apenas uma impressora, terminal de pagamento e caixa registradora são suportados.

#### <a name="printer"></a>Impressora

| Fabricante | Modelo    | Interface | Comentários                  |
|--------------|----------|-----------|---------------------------|
| Epson        | TM-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Epson        | TM-T88   | Personalizado    | Conectado via rede     |
| Star         | TSP650II | Personalizado    | Conectado via rede     |
| Star         | TSP100   | OPOS      | Requer drivers do TSP650II |
| HP           | F7M67AA  | OPOS      | Porta USB               |

#### <a name="payment-terminal"></a>Terminal de pagamento

| Fabricante | Modelo | Interface | Comentários                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personalizado    | Requer personalização do conector de pagamento; conectado via rede e USB |
| VeriFone     | MX915 | Personalizado    | Requer personalização do conector de pagamento; conectado via rede e USB |

#### <a name="cash-drawer"></a>Gaveta de caixa

| Fabricante | Modelo     | Interface | Comentários              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizado    | Conectado via rede |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |
| Epson        |           | Personalizado    | Conectado à impressora de rede Epson via porta DK |


## <a name="troubleshooting"></a>Solução de problemas
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>O Modern POS pode detectar a estação de hardware em sua lista para seleção, mas não pode concluir o emparelhamento

**Solução:** Verifique a lista a seguir com os possíveis pontos de falha:

-   O computador que esta executando o PDV moderno confia no certificado usado no computador que executa a estação de hardware.
    -   Para verificar essa configuração, em um navegador de Web, vá para o seguinte URL: https://&lt;Nome do Computador&gt;:&lt;Número da Porta&gt;/HardwareStation/ping.
    -   Este URL usa um ping para verificar se o computador pode ser acessado, o navegador e indica se o certificado é confiável. (Por exemplo, no Internet Explorer, um ícone de bloqueio é exibido na barra de endereços. Quando você clica nesse ícone, o Internet Explorer verifica se o certificado é confiável atualmente. Você pode instalar o certificado no computador local exibindo os detalhes do certificado que será exibido.)
-   No computador que executa a estação de hardware, a porta que será usada pela estação de hardware é aberta no firewall.
-   A estação de hardware instalou corretamente as informações de conta mercante através da ferramenta de instalação de informações de mercante que é executada no final do instalador de estação de hardware.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>O Modern POS não pode detectar a estação de hardware em sua lista para seleção

**Solução:** Um dos seguintes fatores podem causar este problema:

-   A estação de hardware não foi configurada corretamente no Headquarters. Use as etapas anteriormente neste tópico para verificar se o perfil da estação de hardware e a estação de hardware foram inseridos corretamente.
-   Os trabalhos não foram executados para atualizar a configuração de canal. Neste caso, execute o trabalho 1070 para a configuração de canal.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>O PDV moderno não reflete as novas configurações da caixa registradora.

**Solução:** Feche o lote atual. As alterações na caixa registradora não são atualizadas para o PDV moderno até que o lote atual seja fechado.

### <a name="modern-pos-is-reporting-an-issue-with-a-peripheral"></a>O Modern POS está relatando um problema com um periférico

**Solução:** Eis algumas causas típicas deste problema:

-   Certifique-se de que outros utilitários de configuração de driver de dispositivo estejam fechados. Se esses utilitários estiverem abertos, poderão impedir que o PDV moderno ou a estação de hardware reivindiquem o dispositivo.
-   Se o periférico for compartilhado com vários dispositivos PDV, garanta que ele pertença a uma das seguintes categorias:
    -   Caixa registradora
    -   Impressora de recibo
    -   Terminal de pagamento

    Se o periférico não pertencer a uma dessas categorias, a estação de hardware não será designada para permitir que o periférico seja compartilhado entre vários dispositivos PDV.
-   Às vezes, os drivers de dispositivo pode fazer com que objetos comuns de controle (CCOs) parem de funcionar corretamente. Se um dispositivo tiver sido instalado recentemente, mas não estiver funcionando corretamente ou você notar outros problemas, normalmente é possível resolver o problema reinstalando os CCOs. Para baixar os CCOs, acesse <http://monroecs.com/oposccos_current.htm>.
-   Se você fizer alterações periféricas frequentes durante os testes ou solução de problemas, você pode ter de redefinir o IIS em vez de esperar cache atualizar-se. Para redefinir o IIS, siga estas etapas:
    1.  No menu **Iniciar**, digite **CMD**.
    2.  Em resultados de pesquisa, clique com o botão direito em **Prompt de comando** e, em seguida, clique em **Executar como administrador**.
    3.  Na janela do **Prompt de comando**, digite **iisreset /Restart** e pressione Enter.
    4.  Depois que o IIS reiniciar, reinicie o PDV moderno.
-   Enquanto você estiver fazendo alterações frequentes nos dispositivos periféricos, se você também iniciar e sair do cliente PDV com frequência, o processo de dllhost da sessão de PDV anterior poderá interferir na sessão atual. Neste caso, um dispositivo não pode ser útil até você feche o host (DLL) da biblioteca de link dinâmico que está gerenciando a sessão anterior. Para fechar o host de DLL, siga essas etapas:
    1.  No menu **Iniciar**, digite **Gerenciador de tarefas**.
    2.  Em resultados da pesquisa, clique em **Gerenciador de tarefas**.
    3.  No Gerenciador de tarefas, na guia **Detalhes**, clique no cabeçalho de coluna que está rotulado como **Nome** para classificar a tabela em ordem alfabética.
    4.  Rolar para baixo até você encontrar dllhost.exe.
    5.  Selecione cada host de DLL e, em seguida, clique em **Encerrar tarefa**.
    6.  Depois que os hosts de DLL tiverem sido fechados, reinicie o PDV moderno.


<a name="additional-resources"></a>Recursos adicionais
--------

[Simulador periférico para Commerce](dev-itpro/retail-peripheral-simulator.md)


