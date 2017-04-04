---
title: "Visão geral de varejo periféricos"
description: "Este tópico explica conceitos relacionados de varejo periféricos. Descreve as várias formas os periféricos podem ser conectados ao ponto de venda e os componentes (POS) responsáveis por gerenciar a conexão com o retail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Visão geral de varejo periféricos

Este tópico explica conceitos relacionados de varejo periféricos. Descreve as várias formas os periféricos podem ser conectados ao ponto de venda e os componentes (POS) responsáveis por gerenciar a conexão com o retail.

<a name="concepts"></a>Conceitos
--------

### <a name="pos-registers"></a>Terminais de PDV

Navegação: Clique ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** ** registros. O registro de (POS) de ponto de venda é uma entidade que é usada para definir as características de uma instância específica POS. Essas características incluem ou o perfil de hardware a configuração para os periféricos de varejo que serão usadas no registro, da loja que o registro está mapeado a, e a experiência visual para o usuário que se conecta ao registro.

### <a name="devices"></a>Dispositivos

Navegação: Clique ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** ** dispositivos. Um dispositivo é uma entidade que representa uma instância física de um dispositivo que é mapeado para um registro de POS. Quando um dispositivo for criada, a um registro mapeou POS. A entidade de dispositivo controla informações sobre quando uma registradora de POS é ativada, o tipo de cliente que está sendo usado e o pacote de aplicativo que foi implantado para um dispositivo específico. Dispositivos podem ser mapeados os seguintes tipos de aplicativos: Moderno varejo, o retail POS do nuvem POS, moderno varejo – Windows Phone POS, moderno varejo – Android, e retail – moderno varejista iOS.

### <a name="retail-modern-pos"></a>PDV do Retail Modern

O Retail moderno é o programa POS para o Microsoft Windows. Pode ser implantada Windows 10 sistemas operacionais (OSs).

### <a name="cloud-pos"></a>PDV em Nuvem

O Retail do nuvem é uma versão browser- baseada programa de moderno POS que pode ser acessado em um navegador.

### <a name="modern-pos-for-ios"></a>POS moderno para o iOS

O Retail moderno para o iOS é uma versão iOS- baseada programa de moderno POS que pode ser implantada dispositivos no iOS.

### <a name="modern-pos-for-android"></a>POS para Android moderno

O Retail moderno para Android é uma versão Android- baseada programa de moderno POS que pode ser implantada de dispositivos de Android.

### <a name="pos-peripherals"></a>Periféricos POS

Os periféricos do retail são dispositivos que são suportados explicitamente para funções POS. Esses periféricos são divididos em classes específicas. Para obter mais informações sobre essas classes, consulte “a seção classes dispositivo” este tópico.

### <a name="hardware-station"></a>Estação de hardware

Navegação: Clique ** varejo e comércio ** &gt; ** canais ** &gt; ** lojas ** &gt; ** ** todas as lojas. Selecione uma loja e clique na Guia Rápida **Estações de hardware**. ** Estação de hardware ** a configuração é uma configuração de canal- nível usada para definir as instâncias a lógica em periférica POS será implantada. Esta configuração no canal é usada para determinar características da estação de hardware. Também é usada para listar as estações de hardware disponíveis para uma instância moderna POS em um armazenamento específico. A estação de hardware é criada no programa moderno POS para o Windows. A estação de hardware possível ser implantada independentemente como um programa autônomo de Microsoft Internet information services (IIS). Nesse caso, pode ser acessada pela rede.

### <a name="hardware-profile"></a>Perfil de hardware

Navegação: Clique ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** perfis POS ** &gt; ** ** perfis de hardware. O perfil de hardware é uma lista de dispositivos configurados para um registro POS ou ela de hardware. O perfil de hardware pode ser mapeado diretamente a uma registradora de POS ou uma estação de hardware.

## <a name="devices-classes"></a>Classes de dispositivos
Os periféricos do retail são divididos em classes. Esta seção descreve e dar uma visão geral dos dispositivos do retail moderno suporte.

### <a name="printer"></a>Impressora

As impressoras incluem impressoras tradicionais de recibo do retail e impressoras de página inteira. A impressora estivesse suportada com a fixação de objeto e a incorporação do retail POS OPOS () e o driver do Microsoft Windows faz interface. Até duas impressoras podem ser usadas ao mesmo tempo. Este recurso suporta os cenários qual os recebimentos do cliente de pague-e-pegue são impressos em impressoras de recebimento, enquanto que as ordens do cliente, que têm mais informações, são impressos em uma impressora de página inteira. As impressoras de recebimento podem estar associadas diretamente a um computador em do USB, ser conectadas a rede entre de Ethernet ser conectado, ou por meio de Bluetooth.

### <a name="scanner"></a>Scanner

Até dois scanner de código de barras podem ser usados ao mesmo tempo. Este recurso suporta os cenários onde um scanner mais celular que é necessária para digitalizar grandes ou itens pesados, enquanto um scanner fixo inserido é usado para a maioria dos itens padrão- dimensionados, tempo para agilizar o check-out. Podem ser os scanners suporte com OPOS, plataforma universal (UWP) do Windows, ou a cunha de teclado faz interface. O USB ou Bluetooth podem ser usadas para conexão um scanner a um computador.

### <a name="msr"></a>LTM

Um leitor de tarja magnética (MSR) do USB pode ser configurado usando motoristas OPOS. Se desejar usar um LTM autônomo para transações de pagamento (EFT) de transferência eletrônica de fundos, o LTM deve ser gerenciado por um business connector de pagamento. Os MSRs autônomos podem ser usados para o cartão-fidelidade do cliente, o logon do funcionário, bem o vale-presente, independentemente connector de pagamento.

### <a name="cash-drawer"></a>Caixa registradora

Duas gavetas de caixa podem ser suportadas pelo perfil de hardware. Este recurso habilita duas turno ativo por registro para estar disponível ao mesmo tempo. No caso de um turno compartilhada, ou uma caixa registradora usada por vários dispositivos móveis POS ao mesmo tempo, apenas a caixa registradora seja permitida por perfil de hardware. As gavetas de caixa podem estar associadas diretamente a um computador em do USB, ser conectadas a uma rede, ou estar associadas a uma impressora de recibos por uma interface RJ12. Em alguns casos, as gavetas de caixa também podem ser conectados por meio de Bluetooth.

### <a name="line-display"></a>Display LCD de linhas

Exibe a linha será usado para mostrar produto, saldos da transação, e outras informações úteis ao cliente durante uma transação. Exibe uma linha pode ser vinculada ao computador em do USB usando motoristas OPOS.

### <a name="signature-capture"></a>Assinatura

Dispositivos de assinaturas podem ser vinculados diretamente a um computador em do USB usando motoristas OPOS. Quando a captura de subscrição for configurada, o cliente receberá a assinar o dispositivo. Depois que a assinatura seja fornecida mostrou, o caixa para a aceitação.

### <a name="scale"></a>Balança

Escalas podem ser conectadas ao computador em USP usando motoristas OPOS. Quando um produto que estão marcados como um produto “de” são adicionados a uma transação, o retail leia o peso de escala, adicionar produtos a transação, e usar a quantidade que forneceu a escala.

### <a name="pin-pad"></a>Teclado do PIN

As almofadas (PIN) do número de identificação pessoal são suportadas com OPOS, mas devem ser gerenciadas através de um business connector de pagamento.

### <a name="secondary-display"></a>Exibição secundário

Quando uma exibição secundário for configurada, a exibição do Windows de número 2 será usado para mostrar informações básicas. A finalidade de exibição secundário for suportar ramal independente (ISV) do fornecedor de software, para saída de caixa, a exibição secundário não seja e conteúdo não mostrará limitado.

### <a name="payment-device"></a>Dispositivo de pagamento

O suporte do dispositivo foi implementado de pagamento por meio connector de pagamento. Dispositivos de pagamento podem realizar uma ou várias funções que outras classes de dispositivo fornecem. Por exemplo, um dispositivo de pagamento pode função como um leitor de LTM Card/, a exibição, um dispositivo de assinaturas, ou um teclado do PIN. Suporte para dispositivos de pagamento foi implementado independentemente de suporte autônomo de dispositivo que é fornecido para outros dispositivos incluídos no perfil de hardware.

## <a name="supported-interfaces"></a>Interfaces suporte
### <a name="opos"></a>OPOS

Para ajudar a garantir que o intervalo maior de dispositivos pode ser usado com o Microsoft Dynamics 365 operações - para a venda, varejo OLE para o padrão do setor POS for a plataforma varejista principal de dispositivo que é periférico suportada no Microsoft Dynamics 365 para operações de varejo. OLE para o padrão de pagamento foi gerado por federação varejista university (NRF), que liquida os protocolos de comunicação padrão do setor para dispositivos periféricos de varejo. OPOS é uma implementação muito adotada OLE padrão do POS. Em meados de 1990 s foi desenvolvida e tiver sido atualizada desde várias vezes. OPOS fornece uma arquitetura do driver de dispositivo que permite a integração simples de hardware POS sistemas com Windows no POS. Comunicação de centenas de controles OPOS entre a hardware compatível e softwares POS. Um controle OPOS consiste em duas seções:

-   ** O objeto de controle ** – o objeto de controle para uma classe de dispositivo (como linha exibe) fornece a interface para o programa de software. Serviços de consultoria de Monroe (www.monroecs.com [] (http://www.monroecs.com/)) fornece um conjunto padronizado de objetos de controle OPOS que são conhecidos como objetos (CCOs) comuns de controle. O CCOs é usado para testar o componente do Microsoft Dynamics 365 para operações de varejo. Portanto, ajuda de testes garantem que, se o Microsoft Dynamics 365 para operações - retail suporta uma classe de dispositivo com OPOS, vários tipos de dispositivo pode ser, desde que suporte o fabricante fornece um objeto de serviço que é desenvolvido para OPOS. Você não precisa explicitamente testar cada tipo do dispositivo.
-   ** O objeto de serviço ** – o objeto de serviço fornece a comunicação entre o objeto de CCO (controle) e o dispositivo. Normalmente, o objeto de serviço para um dispositivo for fornecido pelo fabricante do dispositivo. Entretanto, em alguns casos, pode ser necessário baixe o objeto de serviço do site do fabricante. Por exemplo, um objeto mais recente de serviço podem estar disponíveis. Para localizar o endereço do site do fabricante, consulte a documentação de hardware.

[objeto do![e objeto de serviço (]. /media/retail_peripherals_overview01.png)](. O suporte de /media/retail_peripherals_overview01.png) para uma implementação OPOS OLE para ajuda POS que garante se, os fabricantes de dispositivo e os editores POS implementam o padrão corretamente, os sistemas POS e dispositivos suportados podem trabalhar, juntamente se não foram testados anteriormente juntas. ** Observação: ** Suporte OPOS não garante suporte para todos os dispositivos motoristas com OPOS. Microsoft Dynamics 365 para operações de varejo - o primeiro tipo de suportar esse dispositivo, ou classe, com OPOS. Além, os objetos de serviço não podem ser sempre atualizado com a versão mais recente de CCOs. Você também deve estar ciente de que, em geral, a qualidade de objetos de serviço é diferente.

### <a name="windows"></a>Windows

A impressão de recibo em retail é otimizada para OPOS. OPOS tende a ser muito mais rápido da impressão com Windows. Portanto, é recomendável usar OPOS, especialmente em ambientes varejistas onde 40 recibos de coluna são impressos e hora da transação deve ser rápida. Para a maioria de dispositivos, você usará controles OPOS. Entretanto, as impressoras de recebimento de algum OPOS também são compatíveis motoristas do Windows. Usando um motorista de O Windows, é possível acessar as fontes e a impressora as mais recentes de uma rede para vários registros. Contudo, há inconvenientes usá-lo motoristas do Windows. Eis alguns exemplos desses inconvenientes:

-   Quando os motoristas do Windows são usados, imagens estão renderizadas ocorra antes de imprimir. Portanto, imprimir tende sejam mais lento de impressoras em que estiver usando controles OPOS.
-   Dispositivos conectados na impressora margarida- encadeado (“") podem não funcione adequadamente aos motoristas do Windows são usados. Por exemplo, a gaveta de dinheiro não pode abrir, a impressora da guia não pode exprimir como você espera.
-   OPOS também oferece suporte a um conjunto de variáveis mais extensivo particulares vender varejo a impressoras de recibo, como a impressão de papel de corte ou de guia.

Controla se OPOS estão disponíveis para a impressora de O Windows que você está usando, a impressora ainda deverá funcione adequadamente com Microsoft Dynamics 365 para operações de varejo.

### <a name="universal-windows-platform"></a>Plataforma de universal Windows

UWP, em caso de periféricos varejistas, relacionado ao portador de O Windows de dispositivo Plug and Play. Quando um dispositivo Plug and Play estão conectados a uma versão do sistema operacional Windows que suporte o tipo de dispositivo motorista, não é necessário para que o dispositivo foi usado como a finalidade. Por exemplo, se O Windows detecta um dispositivo do alto-falante de Bluetooth, sistema operacional sabe o dispositivo tem ** alto-falante ** classifica o tipo. Portanto, ele gerencia e esse dispositivo como um alto-falante. Nenhuma configuração adicional é necessária. No caso de dispositivos POS, vários dispositivos USB podem ser obstruídos em O Windows, e como reconhecê-los-á dispositivos (HIDs) de interface humana. Entretanto, não consiga determinar os recursos que o dispositivo fornece, pois o dispositivo não especificar a classe, tipo, ou do dispositivo. Windows 10, as classes de dispositivo para scanner de código de barras e os MSRs foram adicionadas. Portanto, se um dispositivo que declara o Windows 10 como um dispositivo de uma dessas classes, Windows escutará eventos do dispositivo em tempo apropriadas. O Retail moderno suporta UWP e MSRs scanner. Portanto, quando estiver pronto para entrada de um deless, e dispositivos um dispositivo que pertença a uma dessas classes é conectado, o dispositivo pode ser usado. Por exemplo, se um scanner de código de barras de UWP é obstruído em um computador com Windows 10, e logon de código de barras estiver configurado para o retail moderno, scanner de código de barras tornar-se-á ativo na tela de logon. Nenhuma configuração adicional é necessária. As classes adicionais de ponto de dispositivos de serviço estão sendo UWP adicionadas ao Windows. Essas classes incluem para classes gavetas de caixa e impressoras de recebimento. Suporte para as novas classes do dispositivo no POS moderno for pendente.

### <a name="keyboard-wedge"></a>Cunha de teclado

Dispositivos de cunha de teclado a enviam dados no computador como esse dados se foram digitados em um teclado. Portanto, por padrão, o campo ativa no POS receberá os dados que são digitalizados ou passados. Em alguns casos, este pode causar comportamento o tipo de dados errado a ser digitalizados no campo de. Por exemplo, um código de barras pode ser verificado em um campo que foi criado para a entrada de dados de cartão de crédito. Em muitos casos, há uma lógica no POS que determina se os dados que são digitalizados são passados ou um código de barras ou um passar o cartão. Portanto, os dados forem controlados adequadamente. Entretanto, quando dispositivos forem OPOS liquidado em vez de dispositivos de cunha do teclado, há mais controle sobre como os dados dos dispositivos podem ser consumidos, porque mais “é conhecido” sobre o dispositivo de que os dados são originadas. Por exemplo, os dados de um scanner de código de barras são reconhecidos automaticamente como um código de barras, e registro associado no base de dados for encontrado mais facilmente e mais rapidamente de que se uma pesquisa de string genérica usada, como no caso dos dispositivos de cunha de teclado.

### <a name="native-printer"></a>Impressora nativo

Quando o tipo é chamado no perfil de hardware) as impressoras nativos (ou “dispositivo” podem ser configuradas para avisar a selecione uma impressora configurada para o computador. Quando uma impressora ** dispositivo ** de tipo se estiver configurada, o retail moderno encontrar um comando de impressão, o usuário será solicitado a selecionar a impressora em uma lista. Esse comportamento difere de comportamento para motoristas de O Windows, pois ** Windows ** a impressora no perfil de hardware não mostra uma lista de impressoras. Em vez disso, requer que uma impressora nomeado seja fornecida ** nome do dispositivo ** no campo.

### <a name="windows"></a>Windows

** Windows ** o tipo de dispositivo for usado apenas para impressoras. Quando uma impressora de O Windows é configurada no perfil de hardware, o nome da impressora específica a ser fornecida. Quando os encontros modernos POS imprimirem eventos, que uma impressora do Windows é configurada, o evento será especificada para a impressora do Windows. O usuário não será solicitado a selecionar uma impressora.

### <a name="network"></a>Rede

as gavetas de caixa, as impressoras de recebimento, e terminais Rede- endereçáveis de pagamento podem ser usados em uma rede, diretamente por meio da estação de hardware de comunicação Interprocess (CPI) que é criada no POS moderno para o aplicativo do Windows ou na estação de hardware do IIS para outros clientes modernos POS.

## <a name="hardware-station-deployment-options"></a>Opções de implementação da estação de hardware
### <a name="ipc-built-in"></a>CPI (acessório)

A estação de hardware de comunicação Interprocess (CPI) é criada no POS moderno para o aplicativo do Windows. Para usar a estação de hardware de CPI, atribuir um perfil de hardware a um registro que use o retail moderno para o aplicativo do Windows. Crie uma estação de hardware de ** dedicado ** tipo para a loja onde o registro será usado. Quando você iniciar o retail moderno, a estação de hardware de CPI estará ativa, e os periféricos POS configurados serão pronto para uso. Se você não requer temporariamente o hardware local por algum motivo, use ** gerenciar estações de hardware ** a operação para desativar recursos da estação de hardware. O Retail moderno também pode usar a estação de hardware de CPI para contato diretamente com os periféricos da rede.

### <a name="iis"></a>IIS

Você pode usar IIS ou a versão autônomo da estação de hardware de duas formas. O descritor “IIS” implica que o aplicativo POS conecta a estação de hardware por meio do Microsoft Internet information services. O aplicativo POS conecta a estação de hardware de IIS nos serviços da Web que executam em um computador onde dispositivos sejam conectados. Quando é usado o IIS, os vários periféricos conectados a uma estação de hardware podem ser usados por qualquer registro que seja do mesmo na rede da estação de hardware do IIS. Embora apenas o retail moderno para Windows inclui suporte interno para varejistas periféricos, todas aplicativos modernas restantes POS devem usar a estação de hardware do IIS para se comunicar com os periféricos POS configurados no perfil de hardware. Portanto, cada instância da estação de hardware de IIS requer um computador que execute o serviço e o aplicativo da Web que se comunica com dispositivos. A estação de hardware de IIS são necessárias para todos os aplicativos modernas POS não do Windows.

#### <a name="dedicated"></a>Dedicado

O Retail moderno usa estações de hardware de ** dedicado ** digita para detectar qual os periféricos estão conectados diretamente ao computador onde descritivo o uso. Entretanto, ** dedicado ** o tipo também pode ser usado para estações de hardware do IIS. Em um cenário tradicional, fixo POS que use o retail do nuvem como aplicativo POS, ** dedicado ** o tipo da estação de hardware é usado para as estações de hardware do que são implantadas no mesmo computador que está executando o retail do nuvem. De uma perspectiva de varejo de periféricos, a estação dedicada de hardware do tem o melhor do varejo para periférico cenários tradicionais, fixos POS. As estações dedicadas de hardware suportam os periféricos que são suportados no perfil de hardware.

#### <a name="shared"></a>Compartilhado

As estações compartilhadas de hardware devem ser usadas para vários dispositivos POS ao curso do dia. As estações compartilhadas de hardware são otimizadas para oferecer suporte apenas gavetas de caixa, impressoras de recebimento, e terminais de pagamento. Você não pode excluí-la diretamente conectar scanner de código de barras autônomos, MSRs, linha exibe, escalas, e outros dispositivos. Caso contrário, os conflitos ocorrerão quando vários dispositivos POS tentam reivindicar simultaneamente os periféricos. É aqui como os conflitos são gerenciados para dispositivos suporte:

-   ** A caixa registradora ** – a caixa registradora seja aberta por meio de um evento que sejam enviados o dispositivo. O único problema que pode ocorrer quando a gaveta de dinheiro é chamada ocorre se a caixa registradora já está aberta. No caso de estações compartilhadas do hardware, a gaveta de dinheiro deve ser definida como ** compartilhado ** o perfil de hardware. Essa configuração impede que o retail POS verifique se a caixa registradora já está aberta quando enviar comandos abertas.
-   ** A impressora de recibos – ** se duas comandos de impressão de recibo são enviados a estação de hardware ao mesmo tempo, uma de comandos possível perdida, dependendo do dispositivo. Alguns dispositivos têm a memória interna ou agrupamento que pode impedir esse problema. Se um comando de impressão não tiver êxito, o caixa receberá uma mensagem de erro e poderá tentar novamente o comando de impressão POS.
-   ** O terminal de pagamento ** – se um caixa tentar oferecer uma transação em um terminal de pagamento que está sendo usado com uma mensagem, o notifica caixa qual o terminal estiver sendo usado e solicita que o caixa tentar novamente mais tarde. Geralmente, os caixas podem consultar um terminal que já está sendo usado e esperará até que outra transação esteja concluída antes que tentem oferecer novamente.

A validação é planejada para uma versão futura, para detectar se dispositivos sem suporte estão configurados para um perfil de hardware que está mapeado para uma estação compartilhada de hardware. Se qualquer dispositivo sem suporte seja detectado, o usuário receberá uma mensagem que indica que os dispositivos não são aceitos para estações compartilhadas de hardware. No caso de estações compartilhadas ** de hardware, selecione quando de oferta ** a opção é definida ** Sim ** em nível de registro. O usuário do pos será solicitado a selecionar uma estação de hardware a proposta é marcada para uma transação no POS. Quando a estação de hardware é selecionada somente no momento de proposta, a seleção da estação de hardware é adicionada diretamente para o fluxo de trabalho do retail para cenários móveis. Como um benefício extra, a exibição da linha no terminal de pagamento não é usada para cenários compartilhados. Se o terminal de pagamento é usado como a exibição, outros usuários podem ser bloqueados uso desse terminal em que a transação seja concluída. Em cenários móveis, as linhas podem ser adicionadas em uma transação durante um período mais longo. ** Portanto, selecione quando de oferta ** a opção é obrigatória para garantir a disponibilidade o melhor do dispositivo.

### <a name="network-peripherals"></a>Periféricos de rede

A designação de rede para dispositivos o perfil de hardware habilita gavetas de caixa, impressoras de recebimento, e terminais de pagamento a serem conectados por meio de uma conexão de rede.

#### <a name="modern-pos-for-windows"></a>POS para O Windows moderno

Você pode especificar o endereço IP de periféricos líquido em dois locais. Se o cliente moderno de O Windows POS usa um conjunto único de periféricos de redes, você deve definir os endereços IP dos dispositivos usando ** IP ** configuração da opção no painel de ações para o próprio registro. No caso dos dispositivos de rede que são compartilhados entre o retail registros, um perfil de hardware com dispositivos de rede atribuídos a ela pode ser mapeado diretamente nela compartilhada de hardware. Para alocar os endereços IP, selecione a estação de hardware ** ** lojas na página, e usar a configuração de ** IP ** a opção ** estações de hardware ** na seção especificar os dispositivos de rede que são atribuídos a essa estação de hardware. As estações de hardware que terão somente dispositivos de rede, não precisa implantar a estação própria de hardware. Nesse caso, a estação de hardware é necessária para agrupar somente conceptualmente dispositivos rede- endereçáveis de acordo com a localização na fábrica.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>Nuble-se o retail POS, moderno para o iOS, e o retail para Android moderno

Lógica às unidades conectaram fisicamente e rede- os periféricos endereçáveis contidos na estação de hardware. Assim, para todos os clientes do retail POS exceto moderno para Windows, ela de hardware de IIS deve ser implantada e ativa para habilitar o retail para comunicar-se com os periféricos, independentemente dos periféricos estão conectados fisicamente a ela de hardware ou resolvidos sobre a rede.

## <a name="setup-and-configuration"></a>Instalação e configuração
### <a name="hardware-station-installation"></a>Instalação da estação de hardware

Para obter informações, consulte configuração [POS da estação de hardware e instalação (retail-hardware-station-configuration-installation.md]).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>POS moderno para a configuração e a configuração de O Windows

Para obter informações, consulte configuração [moderna retail POS e instalação (retail-modern-pos-device-activation.md]).

### <a name="opos-device-setup-and-configuration"></a>Configuração e configuração de dispositivo OPOS

Para obter mais informações sobre os componentes OPOS, consulte a seção “suporte de interfaces” este documento. Normalmente, os motoristas OPOS são fornecidos pelo fabricante do dispositivo. Quando um motorista de dispositivo OPOS é instalado, adicione uma chave do Registro do Windows em um dos seguintes locais:

-   ** sistema de 32 bits: ** LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS\_do HKEY
-   ** sistema de 64 bits: ** LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS\_do HKEY

Na localização de ServiceOPOS, dispositivos configurados estão organizados de acordo com a classe de dispositivo OPOS. Vários motoristas de dispositivo são salvos.

## <a name="supported-scenarios-by-hardware-station-type"></a>Cenários suportados por tipo da estação de hardware
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Suporte do cliente – a estação de hardware de CPI na estação de hardware de IIS

A tabela mostra as topologias e os cenários a implantação de suporte.

| Cliente      | Estação de hardware de CPI | Estação de hardware de IIS |
|-------------|----------------------|----------------------|
| Descritivo de O Windows | Sim                  | Sim                  |
| PDV em Nuvem   | Não                   | Sim                  |
| Android     | Não                   | Sim                  |
| iOS         | Não                   | Sim                  |

### <a name="network-peripherals"></a>Periféricos de rede

Os periféricos da suporte podem ser diretamente na estação de hardware que é criada no POS moderno para o aplicativo do Windows. Para todos os clientes restantes, você deverá implantar ela de hardware do IIS.

| Cliente      | Estação de hardware de CPI | Estação de hardware de IIS |
|-------------|----------------------|----------------------|
| Descritivo de O Windows | Sim                  | Sim                  |
| PDV em Nuvem   | Não                   | Sim                  |
| Android     | Não                   | Sim                  |
| iOS         | Não                   | Sim                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Tipos de dispositivo suportados por tipo da estação de hardware
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>POS moderno para O Windows com ela de hardware de CPI (acessório)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de dispositivo suporte</th>
<th>Interfaces suporte</th>
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
<li>Teclado de cunha (nenhuma configuração é necessária.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Sacador</td>
<td><ul>
<li>OPOS</li>
<li>Apenas uma rede <strong>Observação:</strong> a gaveta pode ser configurada se <strong>Use o deslocamento compartilhada</strong> em caixas.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Gaveta 2</td>
<td><ul>
<li>OPOS</li>
<li>Apenas uma rede <strong>Observação:</strong> a gaveta pode ser configurada se <strong>Use o deslocamento compartilhada</strong> em caixas.</li>
</ul></td>
</tr>
<tr class="even">
<td>Scanner</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nenhuma configuração é necessária.)</li>
<li>Teclado de cunha (nenhuma configuração é necessária.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanner 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (nenhuma configuração é necessária.)</li>
<li>Teclado de cunha (nenhuma configuração é necessária.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Balança</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Teclado do PIN</td>
<td>OPOS (suporte é fornecido à personalização connector de pagamento).</td>
</tr>
<tr class="even">
<td>Assinatura</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Terminal de pagamento </td>
<td><ul>
<li>Suporte personalizado de dispositivo</li>
<li>Rede (para obter mais informações, consulte a documentação do business connector de pagamento).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Todos os clientes modernos POS que têm uma estação dedicada de hardware de IIS

** Observação: ** Quando a estação de hardware de IIS é dedicada “”, há uma relação de um para um entre o cliente do POS e a estação de hardware.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de dispositivo suporte</th>
<th>Interfaces suporte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impressora</td>
<td><ul>
<li>OPOS</li>
<li>O driver de O <strong>Observação:</strong> Windows para impressoras de O Windows em uma rede, o usuário da estação de hardware necessário ter permissão para acessar a impressora.</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="even">
<td>Impressora 2</td>
<td><ul>
<li>OPOS</li>
<li>Driver do Windows</li>
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
<li>A rede <strong>Observação:</strong> gaveta por somente um perfil de hardware pode ser configurada se <strong>Use o deslocamento compartilhada</strong> em caixas.</li>
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
<td>OPOS (suporte é fornecido à personalização connector de pagamento).</td>
</tr>
<tr class="odd">
<td>Sig. captura</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Terminal de pagamento </td>
<td><ul>
<li>Suporte personalizado de dispositivo</li>
<li>Rede (para obter mais informações, consulte a documentação do business connector de pagamento).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Todos os clientes modernos POS que têm uma estação compartilhada de hardware de IIS

** Observação: ** Quando a estação de hardware de IIS, “” será compartilhado vários dispositivos podem usar a estação de hardware ao mesmo tempo. Para esse cenário, você deve usar apenas os dispositivos listados na tabela. Se você tentar compartilhar dispositivos que não são listados aqui, o scanner de código de barras e, MSRs erros ocorrerão quando vários dispositivos tentam reivindicar o mesmo peripheral. Futuramente, como preparação será impedido explicitamente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de dispositivo suporte</th>
<th>Interfaces suporte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impressora</td>
<td><ul>
<li>OPOS</li>
<li>O driver de O <strong>Observação:</strong> Windows para impressoras de O Windows em uma rede, o usuário da estação de hardware necessário ter permissão para acessar a impressora.</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="even">
<td>Impressora 2</td>
<td><ul>
<li>OPOS</li>
<li>Driver do Windows</li>
<li>Rede</li>
</ul></td>
</tr>
<tr class="odd">
<td>Sacador</td>
<td><ul>
<li>OPOS</li>
<li>A rede <strong>Observação:</strong> gaveta por somente um perfil de hardware pode ser configurada se <strong>Use o deslocamento compartilhada</strong> em caixas.</li>
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
<td>Terminal de pagamento </td>
<td><ul>
<li>Suporte personalizado de dispositivo</li>
<li>Rede (para obter mais informações, consulte a documentação do business connector de pagamento).</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Cenários suporte para configuração
Para obter mais informações sobre como criar perfis de hardware para [, consulte definir e manter clientes de canal, inclusive os registros e as estações] de hardware define-maintain-channel-clients-registers-hw-stations.md (). ** Observação: ** Para Microsoft Dynamics 365 para a versão 1611 de operações, o perfil de hardware de estação é usada não. Os atributos configurado anteriormente no perfil de hardware de estação agora são parte da estação de hardware própria.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>POS moderno para O Windows com ela de hardware de CPI (acessório)

Esta configuração é a configuração mais típica para registros tradicionais, fixos POS. Para esse cenário, informações do perfil de hardware é mapeado diretamente ao próprio registro. O número do terminal de TEF deve ser definido no próprio registro. Para configurar essa configuração, rastrear essas etapas.

1.  Crie um perfil de hardware que todos os periféricos necessários sejam configurados.
2.  Mapeie o perfil de hardware a registradora de POS.
3.  Crie uma estação de hardware de ** dedicado ** tipo para a loja onde o registro POS será usado. É uma descrição opcional. ** Observação: ** Você não precisa definir propriedades em nenhuma outra estação de hardware. Todas informações necessárias restante, como o perfil de hardware, virá do próprio registro.
4.  Clique ** varejo e comércio ** &gt; ** TI varejista ** &gt; ** ** agenda de distribuição.
5.  Selecione 1090 ** ** a agenda de distribuição para sincronizar o novo perfil de hardware a loja. Clique ** execução agora ** para sincronizar alterações ao retail.
6.  Selecione 1040 ** ** a agenda de distribuição para sincronizar a novo estação de hardware a loja. Clique ** execução agora ** para sincronizar alterações ao retail.
7.  Instale e ativar o retail para Windows. moderno
8.  Inicie o retail moderno para Windows, e começar a usar os dispositivos periféricos conectados.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Todos os clientes modernos POS que têm uma estação dedicada de hardware de IIS

Essa configuração pode ser usada para todos os clientes modernos POS com ela de hardware que é usada exclusivamente por um registro POS. Para configurar essa configuração, rastrear essas etapas.

1.  Crie um perfil de hardware que todos os periféricos necessários sejam configurados.
2.  Crie uma estação de hardware de ** dedicado ** tipo para a loja onde o registro POS será usado.
3.  Na estação dedicada de hardware, definir as seguintes propriedades:
    -   ** Nome do host ** – o nome do host computador onde a estação de hardware executará. ** Observação: ** O retail do nuvem pode resolver ** localhost ** para determinar o computador local onde o retail do nuvem execução. Entretanto, o certificado necessário para emparelhar o retail do nuvem a estação de hardware também deve ter “localhost” como o nome do computador. Para evitar problemas, recomendamos que você listar cada uma instância de estação dedicada de hardware para o repositório, conforme necessário. Para cada estação de hardware, o nome do host deve ser o nome do computador específico onde a estação de hardware é implantada.
    -   ** Porta ** – a porta a ser usado da estação de hardware comunicar com o cliente moderno POS.
    -   ** O perfil de hardware ** – se o perfil de hardware não foi fornecido na estação própria de hardware, o perfil de hardware que é atribuído ao registro será usado.
    -   ** Número POS EFT ** – a ID de terminal TEF para serem usados quando as autorizações EFT são enviadas. Essa ID é fornecido pelo processador de cartão de crédito.
    -   ** Nome de grupo – ** o pacote da estação de hardware a usar quando a estação de hardware é implantada.

4.  Clique ** varejo e comércio ** &gt; ** TI varejista ** &gt; ** ** agenda de distribuição.
5.  Selecione 1090 ** ** a agenda de distribuição para sincronizar o novo perfil de hardware a loja. Clique ** execução agora ** para sincronizar alterações ao retail.
6.  Selecione 1040 ** ** a agenda de distribuição para sincronizar a novo estação de hardware a loja. Clique ** execução agora ** para sincronizar alterações ao retail.
7.  Instalar a estação de hardware. Para obter mais informações sobre como instalar a estação de hardware, consulte configuração [POS da estação de hardware e instalação (retail-hardware-station-configuration-installation.md]).
8.  Instale e ativar o retail moderno. Para obter mais informações sobre como instalar o moderno, consulte retail [venda varejo ao retail e a instalação modernas] retail-modern-pos-device-activation.md ().
9.  Conectar ao retail moderno, selecione executar ** operações da gaveta **.
10. Inicie ** gerenciar estações de hardware ** a operação.
11. Clique ** gerenciar **.
12. Na página de gerenciamento da estação de hardware, defina a opção para ativar a estação de hardware.
13. Selecione a estação de hardware a ser usada, e clique em pares ** **.
14. Depois da estação de hardware é emparelhada, clique ** ** fechamento.
15. Na página de seleção da estação de hardware, clique na estação selecionada recentemente de hardware para tornar ativo.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Todos os clientes modernos POS que têm uma estação compartilhada de hardware de IIS

Essa configuração pode ser usada para todos os clientes modernos POS que compartilham estações de hardware por outros dispositivos. Para configurar essa configuração, rastrear essas etapas.

1.  Crie um perfil de hardware que os periféricos necessários sejam configurados.
2.  Crie uma estação de hardware de ** compartilhado ** tipo para a loja onde o registro POS será usado.
3.  Na estação compartilhada de hardware, definir as seguintes propriedades:
    -   ** Nome do host ** – o nome do host computador onde a estação de hardware executará.
    -   ** A descrição ** – enviar sms que ajudará a identificar a estação de hardware, como ** devoluções ** ou ** frente ** de armazenamento.
    -   ** Porta ** – a porta a ser usado da estação de hardware comunicar com o cliente moderno POS.
    -   ** O perfil de hardware – ** de estações compartilhadas de hardware, cada estação de hardware deverá ter um perfil de hardware. Os perfis de hardware podem ser compartilhados entre estações de hardware, mas devem ser mapeados cada a estação de hardware. Além, recomendamos que você use turno compartilhadas quando vários dispositivos usam o mesmo estação compartilhada de hardware. Para configurar um turno compartilhada, clique ** varejo e comércio ** &gt; ** a configuração de canal ** &gt; ** configuração POS ** &gt; ** POS analisa ** &gt; ** ** perfis de hardware. Para cada perfil de hardware compartilhado, selecione a caixa registradora, e defina ** gaveta compartilhada de turno ** a opção ** Sim **.
    -   ** Número POS EFT ** – a ID de terminal TEF para serem usados quando as autorizações EFT são enviadas. Essa ID é fornecido pelo processador de cartão de crédito.
    -   ** Nome de grupo – ** o pacote da estação de hardware a usar quando a estação de hardware é implantada.

4.  Repita as etapas 2 e 3 para cada estação de hardware adicional necessária na loja.
5.  Clique ** varejo e comércio ** &gt; ** TI varejista ** &gt; ** ** agenda de distribuição.
6.  Selecione 1090 ** ** a agenda de distribuição para sincronizar o novo perfil de hardware a loja. Clique ** execução agora ** para sincronizar alterações ao retail.
7.  Selecione 1040 ** ** a agenda de distribuição para sincronizar a novo estação de hardware a loja. Clique ** execução agora ** para sincronizar alterações ao retail.
8.  Instalar a estação de hardware em cada computador host que é configurado nas etapas 2 e 3. Para obter mais informações sobre como instalar a estação de hardware, consulte configuração [POS da estação de hardware e instalação (retail-hardware-station-configuration-installation.md]).
9.  Instale e ativar o retail moderno. Para obter mais informações sobre como instalar o moderno, consulte retail [venda varejo ao retail e a instalação modernas] retail-modern-pos-device-activation.md ().
10. Conectar ao retail moderno, selecione executar ** operações da gaveta **.
11. Inicie ** gerenciar estações de hardware ** a operação.

12. Clique ** gerenciar **.
13. Na página de gerenciamento da estação de hardware, defina a opção para ativar a estação de hardware.
14. Selecione a estação de hardware a ser usada, e clique em pares ** **.
15. Repita a etapa 14 para cada estação de hardware que o retail usará. moderno
16. As estações são necessários de hardware emparelhadas depois, clique ** ** fechamento.
17. Na página de seleção da estação de hardware, clique na estação selecionada recentemente de hardware para tornar ativo. ** Observação: ** Se dispositivos que usam diferentes estações de hardware, recomendamos configurar o retail moderno para avisar os caixas para selecionar uma estação de hardware ao iniciar o processo de proposta. Clique ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** ** registros. Selecione o registro, e defina em ** selecione quando a proposta ** a opção ** Sim **. Use ** 1090 ** a agenda de distribuição para sincronizar alterações no base de dados do canal.

## <a name="extensibility"></a>Extensibilidade
Para obter informações sobre os cenários a extensibilidade da estação de hardware, consulte [] extensibilidade da estação de hardware colaborador (- itpro/hardware-station-extensibility.md).

## <a name="security"></a>Segurança
De acordo com padrão de segurança atuais, as seguintes configurações devem ser usados em um ambiente de produção: ** Observação: ** O installer da estação de hardware fará automaticamente para esses edições de Registro como parte da instalação no auto-atendimento.

-   O SSL (SSL) deve ser desabilitada.
-   Apenas a versão 1.2 (TLS) de do Transport Layer Security (ou a versão mais alta atual) devem ser habilitadas ou usado. ** Observação: ** SSL por padrão, e qualquer versão do TLS exceto o TLS 1.2 estão desabilitados. Para editar ou habilitar esses valores, rastrear estas etapas:
    1.  Pressione o logotipo key+R de O Windows para abrir a janela ** ** execução.
    2.  ** Em aberto ** campo, digite Regedit ** **, e clique em OK ** **.
    3.  Se Controle ** da Conta de Usuário ** caixa de mensagem é exibida, clique em Sim ** **.
    4.  ** Editor ** de Registro na janela, navegue ** LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols\_do HKEY **. As seguintes chaves foram inseridas automaticamente para permitir somente o TLS 1.2:
        -   TLS 1.2Server: Enabled=1
        -   TLS 1.2Server: DisabledByDefault=0
        -   TLS 1.2Client: Enabled=1
        -   TLS 1.2Client: DisabledByDefault=0
        -   TLS 1.1Server: Enabled=0
        -   TLS 1.1Client: Enabled=0
        -   TLS 1.0Server: Enabled=0
        -   TLS 1.0Client: Enabled=0
        -   3.0Server SSL: Enabled=0
        -   3.0Client SSL: Enabled=0
        -   2.0Server SSL: Enabled=0
        -   2.0Client SSL: Enabled=0
-   Nenhuma porta de rede adicional deve estar abrir, a menos que é necessária para conhecido, motivos especificados.
-   o compartilhamento de recursos entre origem a ser desabilitado e deve especificar as origens permitidas que são aceitas.
-   Apenas as autoridades de certificação de confiança devem ser usados para obter os certificados que serão usados nos computadores que executam a estação de hardware.

** Observação: ** É muito importante que você examina diretrizes de segurança do IIS e requisitos (PCI) da indústria de cartão de pagamento.

## <a name="peripheral-simulator"></a>Simulador periférico
Para obter informações, consulte simulador [] periférico POS (retail-peripheral-simulator.md).

## <a name="microsofttested-peripheral-devices"></a>Dispositivos periféricos de Microsofttested
### <a name="ipc-built-in-hardware-station"></a>Estação de hardware de CPI (acessório)

Estes periféricos foram testados usando a estação de hardware de CPI que é criada no retail para Windows. moderno

#### <a name="printer"></a>Impressora

| Fabricante | Modelo    | Interface | Comentários                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | OPOS      |                         |
| Epson        | TM-T88V  | OPOS      |                         |
| Estrela         | TSP650II | OPOS      |                         |
| Estrela         | TSP650II | Personalizado    | Conectado na rede   |
| Estrela         | mPOP     | OPOS      | Por meio de Bluetooth conectado |
| HP           | F7M67AA  | OPOS      | Posto USB             |

#### <a name="bar-code-scanner"></a>Scanner de código de barras

| Fabricante  | Modelo         | Interface | Comentários |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Símbolo        | LS2208        | OPOS      |          |
| HP integradas | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Teclado do PIN

| Fabricante | Modelo  | Interface | Comentários                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Requer personalização connector de pagamento |

#### <a name="payment-terminal"></a>Terminal de pagamento 

| Fabricante | Modelo | Interface | Comentários                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinócio      | L5300 | Personalizado    | Requer personalização connector de pagamento                                |
| VeriFone     | MX925 | Personalizado    | Requer personalização connector de pagamento; conectado na rede e do USB |
| VeriFone     | MX915 | Personalizado    | Requer personalização connector de pagamento; conectado na rede e do USB |

#### <a name="cash-drawer"></a>Caixa registradora

| Fabricante | Modelo     | Interface | Comentários                |
|--------------|-----------|-----------|-------------------------|
| Estrela         | mPOP      | OPOS      | Por meio de Bluetooth conectado |
| APG          | Atwood    | Personalizado    | Conectado na rede   |
| Estrela         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Display LCD de linhas

| Fabricante  | Modelo   | Interface | Comentários |
|---------------|---------|-----------|----------|
| HP integradas | G6U79AA | OPOS      |          |
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

### <a name="dedicated-iis-hardware-station"></a>Estação dedicada de hardware de IIS

Estes periféricos foram testados usando (ela não compartilhada dedicada de hardware de IIS com o retail moderno para Windows e nublam-se POS.

#### <a name="printer"></a>Impressora

| Fabricante | Modelo    | Interface | Comentários                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Estrela         | TSP650II | OPOS      |                           |
| Estrela         | TSP650II | Personalizado    | Conectado na rede     |
| Estrela         | TSP100   | OPOS      | Requer motoristas de TSP650II |
| HP           | F7M67AA  | OPOS      | Posto USB               |

#### <a name="bar-code-scanner"></a>Scanner de código de barras

| Fabricante  | Modelo   | Interface | Comentários |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Símbolo        | LS2208  | OPOS      |          |
| HP integradas | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Teclado do PIN

| Fabricante | Modelo  | Interface | Comentários                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Requer personalização connector de pagamento |

#### <a name="payment-terminal"></a>Terminal de pagamento 

| Fabricante | Modelo | Interface | Comentários                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinócio      | L5300 | Personalizado    | Requer personalização connector de pagamento                                |
| VeriFone     | MX925 | Personalizado    | Requer personalização connector de pagamento; conectado na rede e do USB |
| VeriFone     | MX915 | Personalizado    | Requer personalização connector de pagamento; conectado na rede e do USB |

#### <a name="cash-drawer"></a>Caixa registradora

| Fabricante | Modelo     | Interface | Comentários              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizado    | Conectado na rede |
| Estrela         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Display LCD de linhas

| Fabricante  | Modelo   | Interface | Comentários |
|---------------|---------|-----------|----------|
| HP integradas | G6U79AA | OPOS      |          |
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

### <a name="shared-iis-hardware-station"></a>Estação compartilhada de hardware de IIS

Estes periféricos foram testados usando uma estação compartilhada de hardware de IIS com o retail moderno para Windows e nublam-se POS. ** Observação: ** Apenas uma impressora, em terminal de pagamento, e a caixa registradora suporte.

#### <a name="printer"></a>Impressora

| Fabricante | Modelo    | Interface | Comentários                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Estrela         | TSP650II | OPOS      |                           |
| Estrela         | TSP650II | Personalizado    | Conectado na rede     |
| Estrela         | TSP100   | OPOS      | Requer motoristas de TSP650II |
| HP           | F7M67AA  | OPOS      | Posto USB               |

#### <a name="payment-terminal"></a>Terminal de pagamento 

| Fabricante | Modelo | Interface | Comentários                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personalizado    | Requer personalização connector de pagamento; conectado na rede e do USB |
| VeriFone     | MX915 | Personalizado    | Requer personalização connector de pagamento; conectado na rede e do USB |

#### <a name="cash-drawer"></a>Caixa registradora

| Fabricante | Modelo     | Interface | Comentários              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizado    | Conectado na rede |
| Estrela         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Solução de problemas
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>O Retail moderno pode detectar a estação de hardware na lista de seleção, mas não pode concluir emparelhar-se

** Solução: ** Verificar a lista a seguir de pontos reprovação potencial:

-   O computador que está moderno em execução POS depende do certificado usado no computador que executa a estação de hardware.
    -   Verificar, este de instalação em um navegador, vai para a próxima URL: nome&lt;do: https://Computer&gt;&lt;Número&gt;de porta e HardwareStation/ping.
    -   Este URL usa um ping para verificar se o computador pode ser acessado, o navegador e indica se o certificado está confiáveis. (Por exemplo, Internet Explorer, um ícone de bloqueio é exibida na barra de endereços. Quando você clica esse ícone, Internet Explorer verifica se o certificado está confiáveis momento. Você pode instalar o certificado no computador local exibindo os detalhes de certificado que será exibido.)
-   No computador que executa a estação de hardware, a porta que será usada pela estação de hardware é aberta no firewall.
-   A estação de hardware instalou corretamente informações de conta mercante pela ferramenta mercante informativo de instalação que está executando na empresa do installer da estação de hardware.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>O Retail moderno não pode detectar a estação de hardware na lista de seleção

** Solução: ** Qualquer um dos seguintes fatoras pode causar essa saída:

-   A estação de hardware não foi configurado corretamente em sede. Use as etapas anteriormente neste tópico para verificar se o perfil da estação de hardware e a estação de hardware sejam inseridos corretamente.
-   Os trabalhos não foram executados atualizar o canal. Nesse caso, execute os trabalhos 1070 para configuração de canal.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>O Retail moderno não reflete novas configurações da gaveta de dinheiro

** Solução: ** Fechar lote atual. As alterações na gaveta de caixa não são atualizadas ao retail moderno até que o lote é fechado.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>O Retail moderno estiver informando um problema com um peripheral de varejo

** Solução: ** Eis algumas causas típicas desse problema:

-   Verifique se os utilitários de configuração do driver de dispositivo estão fechadas. Se esses utilitários estão abertos, podem impedir que o retail moderno ou a estação de hardware reivindiquem o dispositivo.
-   Se o peripheral de varejo é compartilhado com vários dispositivos POS, garanta que pertence a uma das seguintes categorias:
    -   Caixa registradora
    -   Impressora de recibo
    -   Terminal de pagamento 

    Se o peripheral não pertencer a uma dessas categorias, a estação de hardware não será criada para habilitar o peripheral a ser compartilhado entre vários dispositivos POS.
-   Às vezes, os motoristas de dispositivo pode fazer com os objetos (CCOs) comuns de controle parem de funcionar corretamente. Se um dispositivo tiver sido instalado recentemente, mas não está funcionando corretamente observe ou outros problemas, que você pode resolver o problema reinstalando o CCOs. Para baixar o CCOs, visite< http://monroecs.com/oposccos_current.htm>.
-   Se você fizer alterações periféricas frequentes durante os testes ou solução de problemas, você pode ter de redefinir o IIS em vez de esperar cache para atualizar-se. Para redefinir o IIS, rastrear estas etapas:
    1.  ** Início ** de menu, tipo CMD ** **.
    2.  Os resultados da pesquisa, clique com o botão direito ** prompt de comando, ** ** e em executar como administrador. **
    3.  ** Prompt de comando ** na janela, o tipo iisreset ** /Restart ** e pressione em inserir.
    4.  Depois que o reiniciou, reinicie POS. o moderno
-   Quando você faz alterações frequentes os dispositivos periféricos, se também frequentemente começa e sai do cliente do POS, o processo de dllhost de uma sessão anterior POS pode interferir na sessão atual. Neste caso, um dispositivo não pode ser útil até você feche o host (DLL) da biblioteca de dinâmico- link que a sessão está gerenciando anterior. Para fechar o host do DLL, rastrear estas etapas:
    1.  ** Início ** de menu, digite ** ** gerenciador de tarefas.
    2.  Os resultados da pesquisa, clique ** ** gerenciador de tarefas.
    3.  O gerenciador de tarefas, ** ** detalhes da guia, clique em cabeçalho de coluna que é rotulado ** nome ** para classificar a tabela ordem alfabética por nome.
    4.  Rolar para baixo até você encontra dllhost.exe.
    5.  Selecione cada do DLL host, e em ** tarefa ** final.
    6.  Depois que os do DLL host foram fechados, reinicie POS. o moderno


<a name="see-also"></a>Consulte também
--------

[Venda ao simulador varejo periférico] (retail-peripheral-simulator.md)


