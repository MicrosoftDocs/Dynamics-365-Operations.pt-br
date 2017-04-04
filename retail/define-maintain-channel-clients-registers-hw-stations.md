---
title: "Defina e mantenha clientes de canal, registros, bem estações de hardware"
description: "O wiki aborda como conectar periféricos ao seu Retail POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dee5745670ad86000795f2913f99f49c0f123a00
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-channel-clients-registers-and-hardware-stations"></a>Defina e mantenha clientes de canal, registros, bem estações de hardware

O wiki aborda como conectar periféricos ao seu Retail POS.

**Observação:** para obter instruções específicas de instalação, consulte [Instalação e configuração da estação de hardware de varejo](retail-hardware-station-configuration-installation.md) e [Retail POS modernos autoatendimento download/instalação e ativação de dispositivo de POS modernos e POS de nuvem](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Componentes da chave
Vários componentes são usados para definir as relações entre um armazenamento, do ponto de venda (PDV) ou canais na loja e os periféricos de varejo que usam esses registros ou canais para processar transações. Esta seção descreve cada componente e explica como ele deve ser usado em uma implantação de loja de varejo.

### <a name="pos-registers"></a>Terminais de PDV

Navegação: Clique ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** ** registros. O registro do retail é uma entidade que é usada para definir as características de uma instância específica POS. Essas características incluem ou o perfil de hardware a configuração para os periféricos de varejo que serão usadas no registro, da loja que o registro está mapeado a, e a experiência visual para o usuário que fez logon nesse registro.

### <a name="devices"></a>Dispositivos

Navegação: Clique ** varejo e comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** ** dispositivos. Um dispositivo é uma entidade que representa uma instância física de um dispositivo que é mapeado para um registro de POS. Quando um dispositivo é criado, ele é mapeado para um registro de POS. A entidade de dispositivo controla informações sobre quando uma registradora de POS é ativada, o tipo de cliente que está sendo usado e o pacote de aplicativo que foi implantado para um dispositivo específico. Os dispositivos podem ser de dois tipos: **Retail POS modernos** (MPOS) ou **Retail POS de nuvem** (POS de nuvem).

#### <a name="mpos"></a>MPOS

Os MPOS é um aplicativo de cliente de POS que está instalado no Windows 8.1 ou um sistema operacional posterior baseado em PC. Se o tipo de aplicativo **Retail POS modernos** é mapeado para um dispositivo, o pacote de download pode ser especificado para um determinado dispositivo. O pacote de download pode ser personalizado para incluir diferentes versões do pacote de instalação. A capacidade de implantar pacotes diferentes fornece flexibilidade em casos onde registra POS diferentes, talvez seja necessário integrações diferentes. Os MPOS é implantado em conjunto com uma estação de hardware internos.

#### <a name="cloud-pos"></a>PDV em Nuvem

O Retail do nuvem for retail browser- baseia. Como executar o navegador, o retail do nuvem não Requer o Windows 8.1 ou sistema operacional baseado em CP posterior. Se o tipo de aplicativo **Retail POS de nuvem** é mapeado para um dispositivo específico no back-office, esse dispositivo pode ser usado pelo navegador sem a necessidade de fazer download ou instalar um pacote. Nuvem POS requer uma estação de hardware para usar hardware além de digitalização do código de barras do teclado com base.

### <a name="hardware-profile"></a>Perfil de hardware

Navegação: Clique ** comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** POS analisa ** &gt; ** ** perfis de hardware. Um perfil de hardware identifica o hardware que está conectado a uma registradora de POS ou uma estação de hardware. O perfil de hardware também é usado para especificar os parâmetros de processador de pagamento que devem ser usados durante a comunicação com o kit de desenvolvimento de software (SDK) do pagamento. (O pagamento SDK é implantado como parte de uma estação de hardware).

### <a name="hardware-station"></a>Estação de hardware

Navegação: Clique ** varejo e comércio ** &gt; ** canais ** &gt; ** lojas ** &gt; ** ** todas as lojas. Selecione uma loja e clique na Guia Rápida **Estações de hardware**. Uma estação de hardware é uma instância da lógica de negócios que orienta periféricos de POS. Uma estação de hardware é automaticamente instalada junto com MPOS. Como alternativa, a estação de hardware pode ser instalada como um componente autônomo e então acessada pelo MPOS ou POS de nuvem por meio de um serviço da web. A estação de hardware deve ser definida no nível do canal.

### <a name="hardware-station-profile"></a>Perfil da estação de hardware

Navegação: Clique ** comércio ** &gt; ** configuração de canal ** &gt; ** configuração POS ** &gt; ** perfis POS ** &gt; ** perfis de hardware de estação **. Enquanto a estação de hardware em si especificada no nível de canal inclui informações específicas de instância, como a URL para a estação de hardware, o perfil de estação de hardware inclui informações que podem ser estáticas ou compartilhadas entre várias estações de hardware. Informações estáticas incluem a porta que deve ser usada, o pacote de estação de hardware e o perfil de hardware. Informações estáticas também incluem uma descrição do tipo de estação de hardware que está sendo implantado, como **Check-out **ou **Retorno**, dependendo do hardware que é necessário para cada estação de hardware específico.

## <a name="scenarios"></a>Cenários
### <a name="mpos-with-connected-peripheral-devices"></a>MPOS com dispositivos periféricos conectados

[ponto de venda, tradicional fixo![(]. /media/traditional-300x279.png)](. /media/traditional.png) Para se conectar a MPOS periféricos POS em um cenário tradicional, fixo POS, navegam em primeiro ao próprio registro, e atribuem-lhes um perfil de hardware. Você pode localizar registros POS ** varejo e comércio ** &gt; ** na configuração de canal ** &gt; ** configuração POS ** &gt; ** ** registros. Depois que você atribuiu o perfil de hardware, sincronize alterações no banco de canal usando o agendamento de distribuição "Registros". Você pode encontrar as agendas de distribuição ** varejo e comércio ** &gt; ** o varejista TI ** &gt; ** ** agenda de distribuição. Em seguida, defina uma estação de hardware "local" no canal. Clique ** varejo e comércio ** &gt; ** canais ** &gt; ** lojas ** &gt; ** todas as lojas **, selecione um armazenamento. Em seguida, na Guia Rápida **Estações de Hardware**, clique em **Adicionar** para adicionar uma estação de hardware. Digite uma descrição, digite **localhost** como o nome de host e sincronize as alterações para o canal usando a agenda de distribuição de "Configuração de canal". Você pode encontrar as agendas de distribuição ** varejo e comércio ** &gt; ** o varejista TI ** &gt; ** ** agenda de distribuição. Por fim, no MPOS, use a operação **Selecionar estação de hardware** para selecionar a estação de hardware **localhost**. Definir a estação de hardware **Ativo**. O perfil de hardware usado neste cenário deve vir da registradora do POS propriamente dito. Um perfil de estação de hardware não é necessário para esse cenário. **Observação:** algumas alterações de perfil de hardware, como alterações nas registradoras, exigem que um novo turno seja aberto depois que as alterações são sincronizadas para o canal. **Observação:** nuvem POS deve usar a estação de hardware independente para se comunicar com periféricos de varejo.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>Os MPOS ou nuvem POS com uma estação de hardware independente

alignleft” width= " 300 "align= " label " id= de legenda\[anexo\_340041 "\][periféricos compartilhados] (![. /media/shared-300x254.png)](. Os periféricos compartilhados\[/caption\] de /media/shared.png) neste cenário, ela autônomo de hardware são compartilhados entre clientes e de MPOS de pos do nuvem. Esse cenário requer que você crie um perfil de estação de hardware para especificar o pacote de download, a porta e o perfil de hardware que a estação de hardware usa. Você pode encontrar o perfil de hardware de estação ** varejo e comércio ** &gt; ** na configuração de canal ** &gt; ** configuração POS ** &gt; ** perfis POS ** &gt; ** perfis de hardware de estação **. Após criar o perfil da estação de hardware, navegue para canal varejo específico (** varejo e comércio ** &gt; ** canais ** &gt; ** lojas ** &gt; ** todas as lojas **), e adicione uma nova a estação de hardware. Mapeie essa nova estação de hardware para o perfil de estação de hardware que foi criado anteriormente. Em seguida, forneça uma descrição que ajudará o caixa identificar a estação de hardware. ** Nome do host ** no campo, insira a URL de computador central neste formato: ** https://MachineName:Port/HardwareStation**&lt;&gt;. **&lt;Substituir (MachineName: Porta&gt;** real com o nome do computador da estação de hardware e a porta que é especificada no perfil da estação de hardware.) Para uma estação autônomo de hardware, especifique também o terminal de identificação (EFT) de transferência eletrônica de fundos. Este valor identifica o terminal de TEF que é conectado à estação de hardware quando o conector de pagamento se comunica com o provedor de pagamentos. Em seguida, na máquina estação hardware real, navegue até o canal e selecione estação de hardware. Em seguida, clique em **Download** e instale a estação de hardware. Em seguida, dos MPOS ou POS de nuvem, use a operação **Selecionar estação de hardware** para selecionar estação de hardware que foi instalada anteriormente. Selecione **Par** para estabelecer uma relação de segurança entre o POS e a estação de hardware. Essa etapa deve ser concluída uma vez para cada combinação de um POS e uma estação de hardware. Depois que a estação de hardware é combinada, a mesma operação é usada para ativar a estação de hardware enquanto ele é usado. Para esse cenário, o perfil de hardware deve ser atribuído ao perfil da estação de hardware em vez do próprio registro. Se por algum motivo ela de hardware não tiver um perfil de hardware atribuído diretamente, o perfil de hardware é atribuído ao registro usado

## <a name="client-maintenance"></a>Manutenção do cliente
### <a name="registers"></a>Registradoras

Terminais de PDV são gerenciados principalmente através de registradores próprios e também os perfis são atribuídos aos registros. Atributos que são específicos a um registro individual são gerenciados no nível do registro. Esses atributos incluem a loja em que o registro é usado, o número de registro, a descrição e a ID do terminal de TEF que é específica para o registro em si.

### <a name="pos-profiles"></a>Perfis de PDV

Você poderá encontrar os perfis POS ** varejo e comércio ** &gt; ** na configuração de canal ** &gt; ** configuração POS ** &gt; ** perfis POS **. É útil gerenciar muitos aspectos de um registro através de perfis, porque os perfis podem ser compartilhados entre vários registros. Os perfis podem ser mapeados para um registro individual ou se um perfil é eficaz em uma base de toda a loja, à loja de varejo. As seções a seguir descrevem os perfis de POS e como eles são usados.

#### <a name="offline-profile"></a>Perfil offline

O perfil offline é definido no nível da loja. Ele é usado para especificar as configurações de carregamento para as transações que são executadas em um POS que o registrador não está conectado ao banco de dados do canal.

#### <a name="functionality-profile"></a>Perfil da funcionalidade

O perfil de funcionalidade é definido no nível da loja. Usado para especificar configurações loja gerais sobre as funções que podem ser executadas no POS. Os seguintes recursos são gerenciados com o perfil de funcionalidade. Esses recursos são organizados por Guia Rápida.

-   Guia Rápida **Geral**:
    -   Organização Internacional de Normalização (ISO).
    -   Criar cliente no modo offline.
    -   Perfil de recibo de email.
    -   Autenticação de logon central da equipe.
-   Guia Rápida **Funções**:
    -   Gerenciamento de logon e logon estendido.
    -   Aspectos financeiros e de moeda do POS, como a capacidade de chave em preços e se decimais são necessários para a moeda secundária.
    -   Habilitando o registro de tempo por meio de PDV.
    -   Como os produtos e pagamentos aparecem no POS e nos recebimentos.
    -   Gerenciamento de Fechamento do Dia.
    -   Parâmetros de retenção de transação do banco de dados do canal.
    -   Como os clientes são pesquisados e criados pelo POS.
    -   Como os descontos são calculados.
-   Guia Rápida **Valor**:
    -   Preços máximo e mínimo que são permitidos.
    -   Aplicativo e o cálculo do desconto.
-   Guia Rápida **Códigos informativos**:
    -   Todos os aspectos como códigos informativos são gerenciados no POS. Para obter detalhes, consulte códigos [] de informações information-codes-retail.md ().
-   Guia Rápida **Numeração de recibo**:
    -   Especificar o recebimento de máscaras de numeração, que podem incluir segmentos para o número da loja, o número do terminal, constantes, e se as vendas e cotações, ordens de venda e retorno são impressos em sequências separadas ou se eles todos seguem a mesma sequência.

#### <a name="receipt-profiles"></a>Perfis de recebimento

Os perfis de recibo são atribuídos diretamente às impressoras por meio do perfil de hardware. Eles são usados para especificar os tipos de recebimento que são impressos em uma impressora específica. Os perfis incluem configurações de formatos de recibo que determinam se o recibo será impresso sempre ou se o caixa é solicitado a decidir se o recibo deve ser impresso. Impressoras diferentes também podem usar perfis de recebimento diferente. Por exemplo, 1 impressora é uma impressora de recibos térmica padrão e, portanto, tem menores formatos de recibo. No entanto, impressora 2 é uma impressora de recibos em tamanho normal que é usada para imprimir somente recebimentos de ordem de cliente, que exigem mais espaço.

#### <a name="hardware-profiles"></a>Perfis de hardware

Perfis de hardware são explicados como um componente de configuração do cliente neste artigo. Perfis de hardware são atribuídos diretamente a registradora do POS ou a um perfil de estação de hardware. Eles são usados para especificar os tipos de registro de dispositivos um POS específico ou estação de hardware usada. Perfis de hardware também são usados para especificar as configurações de TEF que são usadas para se comunicar com o SDK do pagamento.

#### <a name="visual-profiles"></a>Perfis visuais

Perfis visuais são atribuídos no nível do registro. Eles são usados para especificar o tema para um registro específico. Os perfis incluem configurações para o tipo de aplicativo usado (MPOS ou POS de nuvem), a cor de destaque e tema, o esquema de fontes, o plano de fundo de logon e o plano de fundo do POS.

### <a name="custom-fields"></a>Campos personalizados

Criar campos personalizados para adicionar campos não são fornecidos saída de caixa ao retail. Para obter mais informações sobre como usar campos personalizados, consulte trabalhando com [costume coloca a postagem de blog] (https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Texto do idioma

Você pode substituir cadeias de caracteres padrão no PDV usando entradas de texto do idioma. Para substituir uma sequência de caracteres no PDV, adicione uma nova linha de texto do idioma. Em seguida, especifique uma ID, a sequência padrão que deve ser substituída e o texto que deve ser mostrado no PDV em vez da cadeia de caracteres padrão.

### <a name="hardware-station-profiles"></a>Perfis das estações de hardware

Os perfis de hardware de estação são explicados neste artigo. Eles são usados para atribuir informações específicas de instância, não estações de hardware.

### <a name="channel-reports-configuration"></a>Configuração de relatórios de canal

Configurar os relatórios que estão disponíveis no canal de varejo na página **Configuração de relatórios de canal de varejo**. Você pode criar novos relatórios, fornecendo a definição XML do relatório e atribuindo o relatório a um grupo de permissão específica no PDV.

### <a name="devices"></a>Dispositivos

Dispositivos são explicados neste artigo. Eles são usados para gerenciar a ativação de um registro de POS específico. Dispositivos também são usados para especificar o aplicativo que é usado para um registro específico e o pacote de instalação que deve ser usado para instalar o cliente MPOS. Aqui estão os estados de ativação do dispositivo:

-   **Pendente** – o dispositivo está pronto para ser ativado.
-   **Ativado** – o dispositivo foi ativado.
-   **Desativado** – o dispositivo foi desativado no back-office ou por meio de PDV.
-   **Desativado** – o dispositivo foi desativado.

Informações adicionais relacionadas à ativação incluem o trabalhador que alterou o status de ativação do dispositivo, um carimbo de data/hora a ativação, e se a configuração do dispositivo foi validada.

### <a name="client-data-synchronization"></a>Sincronização de dados do cliente

Todas as alterações em um cliente de POS, exceto as alterações no status de ativação do dispositivo, devem ser sincronizadas no banco de dados do canal entrem em vigor. Para sincronizar alterações no base de dados do canal, navegue ** varejo e comércio ** ** &gt; varejo específicas TI ** &gt; ** o plano ** de distribuição, e executar o planejamento necessária de distribuição. Para alterações de cliente, você deve executar as agendas de distribuição "Registros" e "Configuração dos canais".


