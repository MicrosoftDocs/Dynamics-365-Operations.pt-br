---
title: Visão geral da integração fiscal dos canais do Commerce
description: Este tópico fornece uma visão geral dos recursos de integração fiscal disponíveis no Dynamics 365 Commerce.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2019-1-16
ms.dyn365.ops.version: 10
ms.openlocfilehash: d2455f775fcf41bbcb1388b2e8053ede8512335d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410283"
---
# <a name="overview-of-fiscal-integration-for-commerce-channels"></a>Visão geral da integração fiscal dos canais do Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Apresentação

Este tópico é uma visão geral dos recursos de integração fiscal disponíveis no Dynamics 365 Commerce. A integração fiscal inclui a integração a vários serviços e dispositivos fiscais que permitem o registro fiscal de vendas de acordo com as leis fiscais locais, destinadas a impedir fraudes fiscais no setor de varejo. Estes são alguns cenários típicos que podem ser cobertos usando a integração fiscal:

- Registrar uma venda em um dispositivo fiscal conectado ao PDV (ponto de venda), como uma impressora fiscal, e imprimir um recibo fiscal para o cliente.
- Enviar com segurança informações relacionadas a vendas e devoluções concluídas no Retail POS a um serviço Web externo operado pela autoridade fiscal.
- Ajudar a garantir a inalterabilidade dos dados de transação de vendas por meio de assinaturas digitais.

A funcionalidade de integração fiscal é uma estrutura que fornece uma solução comum para o desenvolvimento e a personalização da integração entre o Retail POS e os serviços e dispositivos fiscais. Ela também inclui exemplos de integração fiscal que oferecem suporte a cenários básicos para países ou regiões específicos e que funcionam com serviços ou dispositivos fiscais específicos. Um exemplo de integração fiscal consiste em várias extensões de componentes do Commerce e está incluído no SDK (Software Development Kit). Para obter mais informações sobre os exemplos de integração fiscal, consulte [Exemplos de integração fiscal no SDK do Retail](#fiscal-integration-samples-in-the-retail-sdk). Para obter informações sobre como instalar e usar o SDK do Retail, consulte [Arquitetura do SDK (software development kit) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Para oferecer suporte a outros cenários que não têm suporte de um exemplo de integração fiscal, integrar o Retail POS a outros serviços ou dispositivos fiscais ou cobrir requisitos de outros países ou regiões, é necessário estender um exemplo de integração fiscal existente ou criar um novo exemplo usando um existente como modelo.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices"></a>Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais

Um processo de registro fiscal no Retail POS pode consistir em uma ou mais etapas. Cada etapa envolve o registro fiscal de eventos ou transações específicos em um serviço ou dispositivo fiscal. Os seguintes componentes de solução participam do registro fiscal em um dispositivo fiscal conectado a uma Estação de hardware:

- **Extensão CRT (Commerce Runtime)** – esse componente serializa dados de eventos/transações no formato que também é usado para interação com o dispositivo fiscal, analisa respostas do dispositivo fiscal e as armazena no banco de dados do canal. A extensão também define as transações e os eventos específicos que devem ser registrados. Esse componente geralmente é conhecido como *provedor de documentos fiscais*.
- **Extensão Estação de hardware** – esse componente inicializa a comunicação com o dispositivo fiscal, envia solicitações e comandos diretos a esse dispositivo com base nos dados de eventos/transações que são extraídos do documento fiscal e recebe respostas desse dispositivo. Esse componente geralmente é conhecido como *conector fiscal*.

Um exemplo de integração fiscal de um dispositivo fiscal contém as extensões CRT e Estação de hardware para um provedor de documentos fiscais e um conector fiscal, respectivamente. Também contém as seguintes configurações de componentes:

- **Configuração do provedor de documentos fiscais** – Esta configuração define um método de saída e um formato para documentos fiscais. Também contém um mapeamento de dados de impostos e métodos de pagamento para tornar os dados do Retail POS compatíveis com os valores predefinidos no firmware do dispositivo fiscal.
- **Configuração do conector fiscal** – Esta configuração define a comunicação física com o dispositivo fiscal específico.

Um processo de registro fiscal para um terminal de PDV específico é definido por uma configuração correspondente no perfil de funcionalidade do PDV. Para obter mais detalhes sobre como configurar um processo de registro fiscal, carregar configurações do provedor de documentos fiscais e do conector fiscal e alterar seus parâmetros, consulte [Configurar um processo de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

O exemplo a seguir mostra um típico fluxo de execução de registro fiscal para um dispositivo fiscal. O fluxo começa com um evento no PDV (por exemplo, finalização de uma transação de venda) e implementa a seguinte sequência de etapas:

1. O PDV solicita um documento fiscal do CRT.
2. O CRT determina se o evento atual requer registro fiscal.
3. Com base nas configurações do processo de registro fiscal, o CRT identifica um conector fiscal e o provedor de documentos fiscais correspondente para usar no registro fiscal.
4. O CRT executa o provedor de documentos fiscais que gera um documento fiscal (por exemplo, um documento XML) que representa o evento ou a transação.
5. O PDV envia o documento fiscal que o CRT prepara para uma Estação de hardware.
6. A Estação de hardware executa o conector fiscal que processa o documento fiscal e o comunica ao serviço ou dispositivo fiscal.
7. O PDV analisa a resposta do serviço ou dispositivo fiscal para determinar se o registro fiscal foi bem-sucedido.
8. O CRT salva a resposta no banco de dados do canal.

![Esquema da solução](media/emea-fiscal-integration-solution.png "Esquema da solução")

## <a name="error-handling"></a>Tratamento de erros

A estrutura de integração fiscal fornece as seguintes opções para lidar com as falhas durante o registro fiscal:

- **Repetir** – Os operadores podem usar esta opção quando a falha puder ser resolvida rapidamente e o registro fiscal puder ser executado novamente. Por exemplo, essa opção pode ser usada quando o dispositivo fiscal não estiver conectado, a impressora fiscal estiver sem papel ou houver uma obstrução de papel nessa impressora.
- **Cancelar** – Esta opção permite aos operadores adiar o registro fiscal do evento ou da transação atual se ele falhar. Após o adiamento do registro, o operador pode continuar a trabalhar no PDV e concluir qualquer operação que não exija o registro fiscal. Quando qualquer evento que exija o registro fiscal ocorrer no PDV (por exemplo, uma nova transação for aberta), a caixa de diálogo de tratamento de erro aparecerá automaticamente para notificar o operador que a transação anterior não foi registrada corretamente e para fornecer as opções de tratamento de erro.
- **Ignorar** – Os operadores podem usar esta opção quando o registro fiscal puder ser omitido sob condições específicas e as operações normais puderem continuar no PDV. Por exemplo, essa opção pode ser usada quando uma transação de venda cujo registro fiscal tenha falhado puder ser registrada em um diário de papel especial.
- **Marcar como registrado** – Os operadores podem usar esta opção quando a transação for registrada no dispositivo fiscal (por exemplo, um recibo fiscal for impresso), mas uma falha ocorrer quando a resposta fiscal estiver sendo salva no banco de dados do canal.

> [!NOTE]
> As opções **Ignorar** e **Marcar como registrado** devem ser ativadas no processo de registro fiscal antes de serem usadas. Além disso, permissões correspondentes devem ser concedidas aos operadores.

As opções **Ignorar** e **Marcar como registrado** permitem que os códigos informativos capturem algumas informações específicas sobre a falha, como o motivo da falha ou uma justificativa para ignorar o registro fiscal ou marcar a transação como registrada. Para obter mais detalhes sobre como configurar parâmetros de tratamento de erro, consulte [Definir configurações de tratamento de erro](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Registro fiscal opcional

O registro fiscal pode ser obrigatório para algumas operações mas opcional para outras. Por exemplo, o registro fiscal de vendas normais e de devoluções pode ser obrigatório, mas o registro fiscal de operações relacionadas a depósitos de clientes pode ser opcional. Nesse caso, a falha em concluir o registro fiscal de uma venda deve bloquear vendas futuras, mas a falha em concluir o registro fiscal de um depósito de cliente não deve bloquear vendas futuras. Para diferenciar operações obrigatórias e opcionais, recomendamos tratá-las por meio de provedores de documentos diferentes, e que você configure etapas separadas no processo de registro fiscal para esses provedores. O parâmetro **Continuar se houver erro** deve estar habilitado para qualquer etapa relacionada ao registro fiscal opcional. Para obter mais detalhes sobre como configurar parâmetros de tratamento de erro, consulte [Definir configurações de tratamento de erro](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-running-fiscal-registration"></a>Executando o registro fiscal manualmente

Se o registro fiscal de uma transação ou de um evento foi adiado após uma falha (por exemplo, se o operador selecionou **Cancelar** na caixa de diálogo de tratamento de erro), você pode executar novamente o registro fiscal manualmente invocando uma operação correspondente. Para obter mais detalhes, consulte [Habilitar a execução manual do registro fiscal adiado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

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

Quando o registro fiscal de um evento ou uma transação é bem-sucedido, uma transação fiscal é criada no banco de dados do canal e vinculada ao evento ou à transação original. Da mesma forma, se a opção **Ignorar** ou **Marcar como registrado** for selecionada para um registro fiscal com falha, essas informações serão armazenadas em uma transação fiscal. Uma transação fiscal armazena a resposta fiscal do serviço ou dispositivo fiscal. Se o processo de registro fiscal consistir em várias etapas, uma transação fiscal será criada para cada etapa do processo que resultou em um registro com êxito ou falha.

As transações fiscais são transferidas para o Headquarters pelo *trabalho P* com as transações. Na FastTab **Transações fiscais** da página **Transações da loja**, você pode ver as transações fiscais vinculadas às transações.

Uma transação fiscal armazena os seguintes detalhes:

- Detalhes do processo de registro fiscal (processo, grupo do conector, conector etc.). Ela também armazena o número de série do dispositivo fiscal no campo **Número do registro**, se essa informação estiver incluída na resposta fiscal.
- O status do registro fiscal: **Concluído** para registros bem-sucedidos, **Ignorado** se o operador tiver selecionado a opção **Ignorar** para um registro com falha ou **Marcado como registrado** se o operador tiver selecionado a opção **Marcar como registrado**.
- Transações de código informativo relacionadas a uma transação fiscal selecionada. Para exibir as transações de código informativo, na FastTab **Transações fiscais**, selecione uma transação fiscal com status **Ignorado** ou **Marcado como registrado** e, em seguida, selecione **Transações de código informativo**.

## <a name="fiscal-texts-for-discounts"></a>Textos fiscais para descontos

Alguns países ou regiões têm requisitos especiais sobre textos adicionais que devem ser impressos em recibos fiscais quando diferentes tipos de descontos são aplicados. A funcionalidade de integração fiscal permite configurar um texto especial para um desconto que é impresso após a linha de desconto no recibo fiscal. Para descontos manuais, você pode configurar um texto fiscal para o código informativo especificado como **Desconto de produto** no perfil de funcionalidade do PDV. Para obter mais detalhes sobre como configurar textos fiscais para descontos, consulte [Configurar textos fiscais para descontos](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Impressão de relatórios fiscais X e Z

A funcionalidade de integração fiscal oferece suporte à geração de demonstrativos de fechamento do dia específicos ao serviço ou dispositivo fiscal integrado:

- Novos botões que executam operações correspondentes devem ser adicionados ao layout de tela do PDV. Para obter mais detalhes, consulte [Configurar relatórios fiscais X/Z do PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- No exemplo de integração fiscal, essas operações devem ser conciliadas com as operações correspondentes do dispositivo fiscal.

## <a name="fiscal-integration-samples-in-the-retail-sdk"></a>Exemplos de integração fiscal no SDK do Retail

Os seguintes exemplos de integração fiscal estão disponíveis atualmente no SDK do Retail:

- [Exemplo de integração da impressora fiscal para a Itália](emea-ita-fpi-sample.md)
- [Exemplo de integração da impressora fiscal para a Polônia](emea-pol-fpi-sample.md)
- [Integração de serviços de registro fiscal para a Áustria](emea-aut-fi-sample.md)
- [Exemplo de integração de serviços de registro fiscal para a República Tcheca](emea-cze-fi-sample.md)
- [Exemplo de integração da unidade de controle para a Suécia](./emea-swe-fi-sample.md)
- [Exemplo de integração de serviços de registro fiscal para a Alemanha](./emea-deu-fi-sample.md)

A seguinte funcionalidade de integração fiscal também está disponível no SDK do Retail, mas atualmente não aproveita a estrutura de integração fiscal. A migração dessa funcionalidade para a estrutura de integração fiscal está planejada para atualizações posteriores.


- [Assinatura digital para a França](emea-fra-cash-registers.md)
- [Assinatura digital para a Noruega](emea-nor-cash-registers.md)

A seguinte funcionalidade de integração fiscal herdada que está disponível no SDK do Retail não usa a estrutura de integração fiscal e será preterida em atualizações posteriores:

- [Exemplo de integração da unidade de controle para a Suécia (herdada)](./retail-sdk-control-unit-sample.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]