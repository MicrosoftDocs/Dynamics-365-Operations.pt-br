---
title: Visão geral da integração fiscal de canais do Commerce
description: Este artigo fornece uma visão geral dos recursos de integração fiscal disponíveis no Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1812405db3c1e58eaf7cd1df3896f786e7bf026f
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631227"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Visão geral da integração fiscal de canais do Commerce

[!include [banner](../includes/banner.md)]

Este artigo é uma visão geral dos recursos de integração fiscal disponíveis no Dynamics 365 Commerce. 

A integração fiscal inclui a integração a vários serviços e dispositivos fiscais que permitem o registro fiscal de vendas de acordo com as leis fiscais locais, destinadas a impedir fraudes fiscais no setor de varejo. Estes são alguns cenários típicos que podem ser cobertos usando a integração fiscal:

- Registrar uma venda em um dispositivo fiscal conectado ao PDV (ponto de venda), como uma impressora fiscal, e imprimir um recibo fiscal para o cliente.
- Enviar com segurança informações relacionadas a vendas e devoluções concluídas no Retail POS a um serviço Web externo operado pela autoridade fiscal.
- Ajude a garantir a inalterabilidade de dados de transação de vendas por meio de assinaturas digitais.

A funcionalidade de integração fiscal é uma estrutura que fornece uma solução comum para o desenvolvimento e a personalização da integração entre o Retail POS e os serviços e dispositivos fiscais. Ela também inclui exemplos de integração fiscal que oferecem suporte a cenários básicos para países ou regiões específicos e que funcionam com serviços ou dispositivos fiscais específicos. Um exemplo de integração fiscal consiste em várias extensões de componentes do Commerce e está incluído no SDK (Software Development Kit). Para obter mais informações sobre os exemplos de integração fiscal, consulte [Exemplos de integração fiscal no SDK do Commerce](#fiscal-integration-samples-in-the-commerce-sdk). Para obter informações sobre como instalar e usar o SDK do Commerce, consulte [Arquitetura do SDK (software development kit) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Para oferecer suporte a outros cenários que não têm suporte de um exemplo de integração fiscal, integrar o Retail POS a outros serviços ou dispositivos fiscais ou cobrir requisitos de outros países ou regiões, é necessário estender um exemplo de integração fiscal existente ou criar um novo exemplo usando um existente como modelo.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais e serviços

Um processo de registro fiscal no Retail POS pode consistir em uma ou mais etapas. Cada etapa envolve o registro fiscal de eventos ou transações específicos em um serviço ou dispositivo fiscal. Os seguintes componentes de solução participam do registro fiscal em um dispositivo fiscal ou serviço:

- **Provedor de documento fiscal** - Este componente serializa dados de eventos/transações no formato que também é usado para interação com o dispositivo fiscal ou serviço, analisa respostas do dispositivo fiscal ou serviço e as armazena no banco de dados do canal. A extensão também define as transações e os eventos específicos que devem ser registrados.
- **Conector fiscal** – Este componente inicializa a comunicação com o dispositivo fiscal ou serviço, envia solicitações ou comandos diretos a esse dispositivo fiscal ou serviço com base nos dados de eventos/transações que são extraídos do documento fiscal e recebe respostas desse dispositivo fiscal ou serviço

Uma amostra de integração fiscal deve conter as extensões Commerce Runtime (CRT), Estação de hardware, e extensões PDV para um provedor de documentos fiscais e um conector fiscal. Também contém as seguintes configurações de componentes:

- **Configuração do provedor de documentos fiscais** – Esta configuração define um método de saída e um formato para documentos fiscais. Também contém um mapeamento de dados de impostos e métodos de pagamento para tornar os dados do Retail POS compatíveis com os valores predefinidos no firmware do serviço ou dispositivo fiscal.
- **Configuração do conector fiscal** – Esta configuração define a comunicação física com o dispositivo fiscal específico ou serviço.

Um processo de registro fiscal para um terminal de PDV específico é definido por uma configuração correspondente no perfil de funcionalidade do PDV. Para obter mais detalhes sobre como configurar um processo de registro fiscal, carregar configurações do provedor de documentos fiscais e do conector fiscal e alterar seus parâmetros de configuração, consultar [Configurar um processo de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Se você precisar de dispositivos para operações não fiscais, como pesquisa de catálogo de produtos, pesquisa de cliente ou criação de rascunho de transação, poderá selecionar esses como registros com restrições de processo fiscal. Para obter mais informações, consulte [Configurar registros com restrições de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

O seguinte fluxo de registro fiscal típico começa com um evento no POS (por exemplo, a finalização de uma transação de venda) e implementa uma sequência predefinida de etapas que envolvem outros componentes comerciais (como a estação de CRT e Hardware).

1. O PDV solicita uma nota fiscal da estrutura fiscal de integração (FIF).
1. O FIF determina se o evento atual requer ou não registro fiscal.
1. Com base nas configurações do processo de registro fiscal, o FIF identifica um conector fiscal e um provedor de documentos fiscais correspondente para usar no registro fiscal.
1. O FIF executa o provedor de documentos fiscais que gera um documento fiscal (por exemplo, um documento XML) que representa o evento ou a transação.
1. O FIF retorna a nota fiscal gerada para o POS.
1. O PDV solicita que o FIF envie a nota fiscal para o dispositivo ou serviço fiscal.
1. O FIF executa o conector fiscal que processa o documento fiscal e o envia ao serviço ou dispositivo fiscal.
1. O FIF retorna a resposta fiscal (ou seja, a resposta do dispositivo ou serviço fiscal) para o PDV.
1. O PDV analisa a resposta do serviço ou dispositivo fiscal para determinar se o registro fiscal foi bem-sucedido. Conforme necessário, o PDV solicita que o FIF manipule todos os erros ocorridos. 
1. O PDV solicita que o FIF processe e salve a resposta fiscal.
1. O provedor de nota fiscal processa a resposta fiscal. Como parte desse processamento, o provedor de nota fiscal analisa a resposta e extrai os dados estendidos dele.
1. O FIF salva a resposta e os dados estendidos no banco de dados do canal.
1. Conforme necessário, o PDV imprime um recibo por meio de uma impressora de recibo comum que está conectada à estação de hardware. O recibo pode conter os dados necessários da resposta fiscal.
 
O exemplo a seguir mostra um fluxo de execução de registro fiscal para um típico dispositivo fiscal ou serviço.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>O registro fiscal é feito por meio de um dispositivo conectado à estação de hardware

Essa configuração é usada quando um dispositivo fiscal físico, como uma impressora fiscal, está conectado à estação de hardware. Também é aplicável quando a comunicação com um dispositivo ou serviço fiscal é realizada por meio de um software instalado na estação de hardware. Nesse caso, o provedor de nota fiscal está localizado no CRT e o conector fiscal está localizado na estação de hardware.

![O registro fiscal é feito por meio de um dispositivo conectado à estação de hardware.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>O registro fiscal é feito por meio de um serviço externo

Essa configuração é usada quando o registro fiscal é feito por meio de um serviço externo, como um serviço Web que é operado pela autoridade de imposto. Nesse caso, o provedor de nota fiscal e o conector fiscal estão localizados no CRT.

![O registro fiscal é feito por meio de um serviço externo.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>O registro fiscal é feito internamente no formulário CRT

Essa configuração é usada quando não é necessário nenhum dispositivo fiscal ou serviço externo para o registro fiscal. Por exemplo, ele é usado quando o registro fiscal é feito por meio da assinatura digital das transações de vendas. Nesse caso, o provedor de nota fiscal e o conector fiscal estão localizados no CRT.

![O registro fiscal é feito internamente no formulário CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>O registro fiscal é feito por meio de um dispositivo ou serviço na rede local

Essa configuração é usada quando um dispositivo fiscal físico ou um serviço fiscal está presente na rede local do armazenamento e fornece uma API (interface de programação de aplicativo) HTTPS. Nesse caso, o provedor de nota fiscal está localizado no CRT e o conector fiscal está localizado no PDV.

![O registro fiscal é feito por meio de um dispositivo ou serviço na rede local.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Tratamento de erro

A estrutura de integração fiscal fornece as seguintes opções para lidar com as falhas durante o registro fiscal:

- **Repetir** – o operador poderá usar essa opção quando a falha puder ser resolvida rapidamente e o registro fiscal puder ser executado novamente. Por exemplo, essa opção pode ser usada quando o dispositivo fiscal não estiver conectado, a impressora fiscal estiver sem papel ou houver uma obstrução de papel nessa impressora.
- **Cancelar** – esta opção permite que o operador adie o registro fiscal do evento ou da transação atual se houver falha. Após o adiamento do registro, o operador poderá continuar a trabalhar no PDV e poderá concluir qualquer operação que não exija o registro fiscal. Quando qualquer evento que exija o registro fiscal ocorrer no PDV (por exemplo, uma nova transação for aberta), a caixa de diálogo de tratamento de erro aparecerá automaticamente para notificar o operador que a transação anterior não foi registrada corretamente e para fornecer as opções de tratamento de erro.
- **Ignorar** – o operador poderá usar essa opção quando não for possível concluir o registro fiscal da transação ou do evento atual. Por exemplo, se a impressora fiscal não estiver funcionando, **e** o registro fiscal puder ser omitido de acordo com condições específicas. Por exemplo, essa opção pode ser usada quando uma transação de venda cujo registro fiscal tenha falhado puder ser registrada em um diário de papel especial. Depois que o registro fiscal for ignorado, as operações normais poderão continuar no PDV. 
- **Marcar como registrado** – o operador poderá usar essa opção quando a transação ou evento atual foi registrado no dispositivo fiscal. Por exemplo, um recibo fiscal for impresso, mas ocorrer uma falha quando a resposta fiscal estiver sendo salva no banco de dados do canal. Depois de marcar a transação ou o evento atual como registrado, as operações normais poderão continuar no PDV.
- **Adiar** – o operador poderá usar essa opção quando a transação não foi registrada porque o dispositivo ou o serviço de registro não estava disponível **e** uma das seguintes opções for aplicável:
    - Há uma opção de registro fiscal de backup e é possível continuar o processo de registro fiscal para a transação atual. Por exemplo, um [dispositivo fiscal](./latam-bra-cf-e-sat.md#scenario-4-make-a-cash-and-carry-sale-of-goods-by-using-sat-as-contingency-mode) local pode ser uma opção de backup para um serviço de registro fiscal online quando o serviço não está disponível.
    - O registro fiscal poderá ser concluído posteriormente por meio de uma estrutura de integração fiscal. Por exemplo, as transações adiadas poderão ser registradas fiscalmente posteriormente em um lote por uma [funcionalidade separada](./latam-bra-nfce.md#scenario-3-make-a-cash-and-carry-sale-of-goods-in-offline-contingency-mode).
    
    Depois de adiar a transação ou o evento atual, as operações normais poderão continuar no PDV.

> [!WARNING]
> As opções **Ignorar**, **Marcar como registrado** e **Adiar** devem ser consideradas opções de emergência e usadas somente em casos excepcionais. Aborde essas opções de tratamento de erros com seu contador ou assistente jurídico e tenha bom senso antes de habilitá-las. As opções devem ser ativadas no processo de registro fiscal antes de serem usadas. Para garantir que os operadores não as usem regularmente, as permissões correspondentes devem ser concedidas aos operadores.

Uma [transação fiscal](#storing-fiscal-response-in-fiscal-transaction) é criada quando as opções **Ignorar**, **Marcar como registrado** ou **Adiar** são selecionadas, mas a transação fiscal não contém uma resposta fiscal. Isso permite que você capture o evento da falha do registro fiscal. Essas opções também permitem que os códigos informativos capturem algumas informações específicas sobre uma falha, como o motivo da falha ou uma justificativa para ignorar o registro fiscal ou marcar a transação como registrada. Para obter mais detalhes sobre como configurar parâmetros de tratamento de erro, consulte [Definir configurações de tratamento de erro](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Registro fiscal opcional

O registro fiscal pode ser obrigatório para algumas operações mas opcional para outras. Por exemplo, o registro fiscal de vendas normais e de devoluções pode ser obrigatório, mas o registro fiscal de operações relacionadas a depósitos de clientes pode ser opcional. Nesse caso, a falha em concluir o registro fiscal de uma venda deve bloquear vendas futuras, mas a falha em concluir o registro fiscal de um depósito de cliente não deve bloquear vendas futuras. Para diferenciar operações obrigatórias e opcionais, recomendamos tratá-las por meio de provedores de documentos diferentes, e que você configure etapas separadas no processo de registro fiscal para esses provedores. O parâmetro **Continuar se houver erro** deve estar habilitado para qualquer etapa relacionada ao registro fiscal opcional. Para obter mais detalhes sobre como configurar parâmetros de tratamento de erro, consulte [Definir configurações de tratamento de erro](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Executar novamente o registro fiscal manualmente

Se o registro fiscal de uma transação ou de um evento foi adiado após uma falha (por exemplo, se o operador selecionou **Cancelar** na caixa de diálogo de tratamento de erro), você pode executar novamente o registro fiscal manualmente invocando uma operação correspondente. Para obter mais detalhes, consulte [Habilitar a execução manual do registro fiscal adiado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).

### <a name="fiscal-registration-health-check"></a>Verificação de integridade do registro fiscal

O procedimento de verificação de integridade para registros fiscais verifica a disponibilidade do dispositivo fiscal ou do serviço quando ocorrem eventos específicos. Se o registro fiscal não puder ser concluído no momento, o operador será notificado antecipadamente.

O PDV executa a verificação de integridade quando ocorrem os seguintes eventos:

- Uma nova transação é aberta.
- Uma transação suspensa é recuperada.
- Uma transação de venda ou de devolução é finalizada.

Se houver falha na verificação de integridade, o PDV exibirá a caixa de diálogo de verificação de integridade. Essa caixa de diálogo fornece os seguintes botões:

- **OK** — esse botão permite que o operador ignore um erro de verificação de integridade e continue o processamento da operação. Os operadores só poderão selecionar esse botão se a permissão **Permitir ignorar o erro de verificação de integridade** estiver habilitada para eles.
- **Cancelar** — se o operador selecionar esse botão, o PDV cancelará a última ação (por exemplo, um item não será adicionado a uma nova transação.)

> [!NOTE]
> A verificação de integridade será executada somente se a operação atual exigir o registro fiscal e se o parâmetro **Continuar se houver erro** estiver desabilitado para a etapa atual do processo de registro fiscal. Para obter mais detalhes, consulte [Definir configurações de tratamento de erro](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Armazenamento da resposta fiscal na transação fiscal

Quando o registro fiscal de um evento ou uma transação é bem-sucedido, uma transação fiscal é criada no banco de dados do canal e vinculada ao evento ou à transação original. Da mesma forma, se a opção **Ignorar**, **Marcar como registrado** ou **Adiar** for selecionada para um registro fiscal com falha, essas informações serão armazenadas em uma transação fiscal. Uma transação fiscal armazena a resposta fiscal do serviço ou dispositivo fiscal. Se o processo de registro fiscal consistir em várias etapas, uma transação fiscal será criada para cada etapa do processo que resultou em um registro com êxito ou falha.

As transações fiscais são transferidas para o headquarters pelo *trabalho P* com as transações. Na FastTab **Transações fiscais** da página **Transações da loja**, você pode ver as transações fiscais vinculadas às transações.

Uma transação fiscal armazena os seguintes detalhes:

- Detalhes do processo de registro fiscal (processo, grupo do conector, conector etc.). Ela também armazena o número de série do dispositivo fiscal no campo **Número do registro**, se essa informação estiver incluída na resposta fiscal.
- O status do registro fiscal: **Concluído** para registros bem-sucedidos, **Ignorado** se o operador tiver selecionado a opção **Ignorar** para um registro com falha ou **Marcado como registrado** se o operador tiver selecionado a opção **Marcar como registrado** ou **Adiado** se o operador tiver selecionado a opção **Adiado**.
- Transações de código informativo relacionadas a uma transação fiscal selecionada. Para exibir as transações de código informativo, na guia rápida **Transações fiscais**, selecionar uma transação fiscal com status de **Ignorado**, ou **Marcado como registrado** ou **Adiado** e, em seguida, selecionar **Transações de código informativo**.

Ao selecionar **Dados estendidos**, você também pode exibir algumas propriedades da transação fiscal. A lista de propriedades que pode ser exibida é específica da funcionalidade de registro fiscal que gerou a transação fiscal. Por exemplo, você pode exibir a assinatura digital, o número sequencial, a impressão digital do certificado, a identificação do algoritmo hash e outras propriedades da transação fiscal para a funcionalidade de assinatura digital da França.

## <a name="fiscal-texts-for-discounts"></a>Textos fiscais para descontos

Alguns países ou regiões têm requisitos especiais sobre textos adicionais que devem ser impressos em recibos fiscais quando diferentes tipos de descontos são aplicados. A funcionalidade de integração fiscal permite configurar um texto especial para um desconto que é impresso após a linha de desconto no recibo fiscal. Para descontos manuais, você pode configurar um texto fiscal para o código informativo especificado como **Desconto de produto** no perfil de funcionalidade do PDV. Para obter mais detalhes sobre como configurar textos fiscais para descontos, consulte [Configurar textos fiscais para descontos](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Impressão de relatórios fiscais X e Z

A funcionalidade de integração fiscal oferece suporte à geração de demonstrativos de fechamento do dia específicos ao serviço ou dispositivo fiscal integrado:

- Novos botões que executam operações correspondentes devem ser adicionados ao layout de tela do PDV. Para obter mais detalhes, consulte [Configurar relatórios fiscais X/Z do PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- No exemplo de integração fiscal, essas operações devem ser conciliadas com as operações correspondentes do dispositivo fiscal.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Exemplos de integração fiscal no SDK do Commerce

Os seguintes exemplos de integração fiscal estão disponíveis atualmente no SDK do Commerce:

- [Exemplo de integração da impressora fiscal para a Itália](./emea-ita-fpi-sample.md)
- [Exemplo de integração da impressora fiscal para a Polônia](./emea-pol-fpi-sample.md)
- [Integração de serviços de registro fiscal para a Áustria](./emea-aut-fi-sample.md)
- [Exemplo de integração de serviços de registro fiscal para a República Tcheca](./emea-cze-fi-sample.md)
- [Exemplo de integração da unidade de controle para a Suécia](./emea-swe-fi-sample.md)
- [Exemplo de integração de serviços de registro fiscal para a Alemanha](./emea-deu-fi-sample.md)
- [Exemplo de integração da impressora fiscal para a Rússia](./rus-fpi-sample.md)

A funcionalidade de integração fiscal a seguir também é implementada usando a estrutura de integração fiscal, mas ela está disponível pronta para uso e não está incluída no SDK do Commerce:

- [Registro fiscal do Brasil](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Assinatura digital para a França](./emea-fra-cash-registers.md)

A seguinte funcionalidade de integração fiscal também está disponível no SDK do Commerce, mas atualmente não aproveita a estrutura de integração fiscal. A migração dessa funcionalidade para a estrutura de integração fiscal está planejada para atualizações posteriores.

- [Assinatura digital para a Noruega](./emea-nor-cash-registers.md)

A seguinte funcionalidade de integração fiscal herdada que está disponível no SDK do Commerce não usa a estrutura de integração fiscal e será preterida em atualizações posteriores:

- [Exemplo de integração da unidade de controle para a Suécia (herdada)](./retail-sdk-control-unit-sample.md)
- [Assinatura digital para a França (herdada)](./emea-fra-deployment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
