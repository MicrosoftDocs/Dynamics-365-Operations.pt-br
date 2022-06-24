---
title: Conectar periféricos ao ponto de venda (PDV)
description: Este artigo aborda como conectar periféricos ao seu Retail POS.
author: BrianShook
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ffee75e1713c7c9d31b1d023cd055c2f1a3fc43d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897099"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Conectar periféricos ao ponto de venda (PDV)

[!include [banner](includes/banner.md)]

Este artigo aborda como conectar periféricos ao seu Retail POS.

> [!NOTE]
> Para obter instruções de instalação específicas, consulte [Configurar e instalar Retail Hardware Station](retail-hardware-station-configuration-installation.md) e [Configurar, instalar e ativar o Modern POS (MPOS)](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Componentes da chave

Vários componentes são usados para definir as relações entre uma loja, terminais do ponto de venda (PDV) ou canais na loja e os periféricos que esses terminais ou canais usam para processar transações. Esta seção descreve cada componente e explica como ele deve ser usado em uma implantação de loja.

### <a name="pos-registers"></a>Terminais de PDV

Navegação: Clique em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Terminais**.

O terminal de PDV é uma entidade usada para definir as características de uma instância específica do PDV. Essas características incluem o perfil ou configuração de hardware para os periféricos que serão usados no registro, a loja em que o registro está mapeado, e a experiência visual para o usuário que se conecta ao registro.

### <a name="devices"></a>Dispositivos

Navegação: Clique em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Dispositivos**.

Um dispositivo é uma entidade que representa uma instância física de um dispositivo que é mapeado para um registro de POS. Quando um dispositivo é criado, ele é mapeado para um registro de POS. A entidade de dispositivo controla informações sobre quando uma registradora de POS é ativada, o tipo de cliente que está sendo usado e o pacote de aplicativo que foi implantado para um dispositivo específico. Os dispositivos podem ser de dois tipos: **Retail POS modernos** (MPOS) ou **Retail POS de nuvem** (POS de nuvem).

#### <a name="mpos"></a>MPOS

Os MPOS é um aplicativo de cliente de POS que está instalado no Windows 8.1 ou um sistema operacional posterior baseado em PC. Se o tipo de aplicativo **Retail POS modernos** é mapeado para um dispositivo, o pacote de download pode ser especificado para um determinado dispositivo. O pacote de download pode ser personalizado para incluir diferentes versões do pacote de instalação. A capacidade de implantar pacotes diferentes fornece flexibilidade em casos onde registra POS diferentes, talvez seja necessário integrações diferentes. Os MPOS é implantado em conjunto com uma estação de hardware internos.

#### <a name="cloud-pos"></a>PDV em Nuvem

O PDV em nuvem é um PDV com base no navegador. Como ele é executado no navegador, o PDV em nuvem não requer Windows 8.1 ou um sistema operacional posterior baseado em PC. Se o tipo de aplicativo **PDV em Nuvem do Retail** for mapeado para um dispositivo específico no headquarters, esse dispositivo poderá ser usado pelo navegador sem a necessidade de baixar ou instalar um pacote. Nuvem POS requer uma estação de hardware para usar hardware além de digitalização do código de barras do teclado com base.

### <a name="hardware-profile"></a>Perfil de hardware

Navegação: Vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de hardware**.

Um perfil de hardware identifica o hardware que está conectado a um terminal de PDV por meio de uma estação de hardware integrada ou compartilhada. O perfil de hardware também é usado para especificar os parâmetros de processador de pagamento que devem ser usados durante a comunicação com o kit de desenvolvimento de software (SDK) do pagamento. O pagamento SDK é implantado como parte de uma estação de hardware.

### <a name="hardware-station"></a>Estação de hardware

Navegação: acesse **Varejo e Comércio \> Canais \> Lojas \> Todas as lojas**, selecione uma loja e, em seguida, selecione a Guia Rápida **Estações de hardware**.

Uma estação de hardware é uma instância da lógica de negócios que orienta periféricos de POS. Uma estação de hardware é automaticamente instalada junto com MPOS. Como alternativa, a estação de hardware pode ser instalada como um componente autônomo e então acessada pelo MPOS ou POS de nuvem por meio de um serviço da web. A estação de hardware deve ser definida no nível do canal.

## <a name="scenarios"></a>Cenários

### <a name="mpos-with-connected-peripheral-devices"></a>MPOS com dispositivos periféricos conectados

[![Ponto de venda fixo tradicional.](./media/traditional-300x279.png)](./media/traditional.png)

Para conectar os MPOS periféricos POS em um cenário de POS tradicional fixo, primeiro navegue até o registro em si e atribua um perfil de hardware a ele. Você pode encontrar os terminais de PDV em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Terminais**. 

Depois de atribuir o perfil de hardware, sincronize as alterações com o banco de dados do canal usando a agenda de distribuição **Terminais**. Você pode encontrar as agendas de distribuição em **Varejo e Comércio** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição**. 

Em seguida, defina uma estação de hardware dedicada no canal. Acesse **Varejo e Comércio \> Canais \> Lojas \> Todas as lojas** e selecione uma loja. 

Em seguida, na Guia Rápida **Estações de Hardware**, selecione **Adicionar** para adicionar uma estação de hardware. Selecione **Dedicado** como tipo de estação de hardware e digite uma descrição. O campo **Perfil de hardware** pode ser deixado em branco, pois o perfil de hardware usado neste cenário é proveniente do próprio terminal de PDV. Em seguida, sincronize as alterações no canal usando a programação de distribuição **Configuração de canal**. Você pode encontrar as agendas de distribuição em **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**. 

Por fim, em MPOS, use a operação **Selecionar estação de hardware** para selecionar a estação de hardware que corresponde ao valor inserido anteriormente para a descrição e defina a estação de hardware como **Ativa**. 

> [!NOTE]
> - Algumas alterações de perfil de hardware, como alterações nas registradoras, exigem que um novo turno seja aberto após a sincronização das alterações para o canal.
> - O Cloud POS deve usar o Hardware Station independente para se comunicar com os periféricos.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>Os MPOS ou nuvem POS com uma estação de hardware independente

[![Periféricos compartilhados.](./media/shared-300x254.png)](./media/shared.png)

Nesse cenário, uma estação de hardware independente é compartilhada entre clientes MPOS e PDV de nuvem. Esse cenário requer que você crie uma estação de hardware compartilhada e especifique o pacote de download, a porta e o perfil de hardware que a estação de hardware usa. Você define uma nova estação de hardware selecionando a Guia Rápida **Estações de hardware** no canal específico (**Varejo e Comércio \> Canais \> Lojas \> Todas as lojas**) e adicionando uma nova estação de hardware do tipo **Compartilhada**. 

Em seguida, forneça uma descrição que ajudará o caixa identificar a estação de hardware. No campo **Nome do host**, digite a URL do host de máquina no seguinte formato: `https://<MachineName:Port>/HardwareStation`. (Substitua **&lt;MachineName:Port&gt;** pelo nome de máquina real da estação de hardware.) Para uma estação de hardware independente, também é necessário especificar a transferência eletrônica de fundos (TEF) ID do terminal. Este valor identifica o terminal de TEF que é conectado à estação de hardware quando o conector de pagamento se comunica com o provedor de pagamentos. 

Em seguida, na máquina que hospedará a estação de hardware, vá para o canal no headquarters e selecione a estação de hardware. Em seguida, selecione **Download** para baixar o instalador de estação de hardware e instale a estação de hardware. Para mais informações sobre como instalar a estação de hardware, consulte [Configurar e instalar a estação de hardware do Retail](retail-hardware-station-configuration-installation.md). 

Em seguida, dos MPOS ou POS de nuvem, use a operação **Selecionar estação de hardware** para selecionar estação de hardware que foi instalada anteriormente. Selecione **Par** para estabelecer uma relação de segurança entre o POS e a estação de hardware. Essa etapa deve ser concluída uma vez para cada combinação de um POS e uma estação de hardware. 

Depois que a estação de hardware é combinada, a mesma operação é usada para ativar a estação de hardware enquanto ele é usado. Para este cenário, o perfil de hardware deve ser atribuído à estação de hardware compartilhada em vez do próprio registro. Se nenhum perfil de hardware for atribuído diretamente a uma estação de hardware por algum motivo, o perfil de hardware atribuído ao registro será usado.

## <a name="client-maintenance"></a>Manutenção do cliente

### <a name="registers"></a>Registradoras

Terminais de PDV são gerenciados principalmente através de registradores próprios e também os perfis são atribuídos aos registros. Atributos que são específicos a um registro individual são gerenciados no nível do registro. Esses atributos incluem a loja em que o registro é usado, o número de registro, a descrição e a ID do terminal de TEF que é específica para o registro em si.

### <a name="pos-profiles"></a>Perfis de PDV

Você pode encontrar os perfis de PDV em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV**. É útil gerenciar muitos aspectos de um registro através de perfis, porque os perfis podem ser compartilhados entre vários registros. Os perfis podem ser mapeados para um terminal individual ou, se um perfil é eficaz na loja inteira, para a loja. As seções a seguir descrevem os perfis de POS e como eles são usados.

#### <a name="offline-profile"></a>Perfil offline

O perfil offline é definido no nível da loja. Ele é usado para especificar as configurações de carregamento para as transações que são executadas em um POS que o registrador não está conectado ao banco de dados do canal.

#### <a name="functionality-profile"></a>Perfil da funcionalidade

O perfil de funcionalidade é definido no nível da loja. É usado para especificar configurações de loja sobre as funções que podem ser executadas no PDV. Os seguintes recursos são gerenciados com o perfil de funcionalidade. Esses recursos são organizados por Guia Rápida.

- Guia Rápida **Geral**:

    - Organização Internacional de Normalização (ISO).
    - Criar cliente no modo offline.
    - Perfil de recibo de email.
    - Autenticação de logon central da equipe.

- Guia Rápida **Funções**:

    - Gerenciamento de logon e logon estendido.
    - Aspectos financeiros e de moeda do POS, como a capacidade de chave em preços e se decimais são necessários para a moeda secundária.
    - Habilitando o registro de tempo por meio de PDV.
    - Como os produtos e pagamentos aparecem no POS e nos recebimentos.
    - Gerenciamento de Fechamento do Dia.
    - Parâmetros de retenção de transação do banco de dados do canal.
    - Como os clientes são pesquisados e criados pelo POS.
    - Como os descontos são calculados.

- Guia Rápida **Valor**:

    - Preços máximo e mínimo que são permitidos.
    - Aplicativo e o cálculo do desconto.

- Guia Rápida **Códigos informativos**:

    - Todos os aspectos como códigos informativos são gerenciados no PDV. Para obter detalhes, consulte [Códigos informativos e grupos de códigos informativos](info-codes-retail.md).

- Guia Rápida **Numeração de recibo**:

    - Especificar o recebimento de máscaras de numeração, que podem incluir segmentos para o número da loja, o número do terminal, constantes, e se as vendas e cotações, ordens de venda e retorno são impressos em sequências separadas ou se eles todos seguem a mesma sequência.

#### <a name="receipt-profiles"></a>Perfis de recibo

Os perfis de recibo são atribuídos diretamente às impressoras por meio do perfil de hardware. Eles são usados para especificar os tipos de recebimento que são impressos em uma impressora específica. Os perfis incluem configurações de formatos de recibo que determinam se o recibo será impresso sempre ou se o caixa é solicitado a decidir se o recibo deve ser impresso. Impressoras diferentes também podem usar perfis de recebimento diferente. Por exemplo, 1 impressora é uma impressora de recibos térmica padrão e, portanto, tem menores formatos de recibo. No entanto, impressora 2 é uma impressora de recibos em tamanho normal que é usada para imprimir somente recebimentos de ordem de cliente, que exigem mais espaço. Para obter mais informações, consulte [Configurar um perfil de recibo](configure-emailed-receipt-formats.md#configure-a-receipt-profile).

#### <a name="hardware-profiles"></a>Perfis de hardware

Perfis de hardware são explicados como um componente de configuração do cliente neste artigo. Os perfis de hardware são atribuídos diretamente ao terminal de PDV ou a uma estação de hardware compartilhada e são usados para especificar os tipos de dispositivos usados por um determinado terminal de PDV ou estação de hardware. Perfis de hardware também são usados para especificar as configurações de TEF que são usadas para se comunicar com o SDK do pagamento.

#### <a name="visual-profiles"></a>Perfis visuais

Os perfis visuais são usados para especificar o tema para um registro específico e são atribuídos no nível do registro. Os perfis incluem configurações para o tipo de aplicativo usado (MPOS ou POS de nuvem), a cor de destaque e tema, o esquema de fontes, o plano de fundo da página de entrada e o plano de fundo do PDV. Para obter mais informações, consulte [Criar perfis visuais de ponto de venda (PDV)](tasks/create-pos-visual-profile-2016-02.md). 

### <a name="custom-fields"></a>Campos personalizados

Você pode criar campos personalizados para adicionar campos que não sejam fornecidos prontos para o PDV. Para obter mais informações sobre como usar campos personalizados, consulte a postagem do blog [Trabalhando com campos personalizados](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Texto do idioma

Você pode substituir cadeias de caracteres padrão no PDV usando entradas de texto do idioma. Para substituir uma sequência de caracteres no PDV, adicione uma nova linha de texto do idioma. Em seguida, especifique uma ID, a sequência padrão que deve ser substituída e o texto que deve ser mostrado no PDV em vez da cadeia de caracteres padrão.

### <a name="channel-reports-configuration"></a>Configuração de relatórios de canal

Você configura os relatórios que estão disponíveis no canal na página **Configuração de relatórios de canal**. Você pode criar novos relatórios, fornecendo a definição XML do relatório e atribuindo o relatório a um grupo de permissão específica no PDV.

### <a name="devices"></a>Dispositivos

Dispositivos são explicados neste artigo. Eles são usados para gerenciar a ativação de um registro de POS específico. Dispositivos também são usados para especificar o aplicativo que é usado para um registro específico e o pacote de instalação que deve ser usado para instalar o cliente MPOS. Aqui estão os estados de ativação do dispositivo:

- **Pendente** – o dispositivo está pronto para ser ativado.
- **Ativado** – o dispositivo foi ativado.
- **Desativado** – O dispositivo foi desativado no headquarters ou por meio do PDV.
- **Desativado** – o dispositivo foi desativado.

Informações adicionais relacionadas à ativação incluem o trabalhador que alterou o status de ativação do dispositivo, um carimbo de data/hora a ativação, e se a configuração do dispositivo foi validada.

### <a name="client-data-synchronization"></a>Sincronização de dados do cliente

Todas as alterações em um cliente de POS, exceto as alterações no status de ativação do dispositivo, devem ser sincronizadas no banco de dados do canal entrem em vigor. Para sincronizar as alterações com o banco de dados de canal, navegue até **Varejo e Comércio** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição** e execute a agenda de distribuição necessária. Para alterações de cliente, você deve executar as agendas de distribuição **Terminais** e **Configuração do canal**.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e instalar Retail Hardware Station](retail-hardware-station-configuration-installation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
