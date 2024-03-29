---
title: Configurar a integração fiscal para canais do Commerce
description: Este artigo fornece diretrizes para configurar a funcionalidade de integração fiscal para canais do Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 28097341c7b39660b834eb81786c3f56045e1496
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631414"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Configurar a integração fiscal para canais do Commerce

[!include [banner](../includes/banner.md)]

Este artigo fornece diretrizes para configurar a funcionalidade de integração fiscal para canais do Commerce. Para obter mais informações sobre a integração fiscal, consulte [Visão geral da integração fiscal dos canais do Commerce](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>Habilitar recursos no Commerce headquarters

Para habilitar recursos relacionados à funcionalidade de integração fiscal para canais do Commerce, siga estas etapas:

1. No Commerce headquarters, Acesse **Administração do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. Encontre e habilite os seguintes recursos:

    - **Integração fiscal direta de terminais de PDV** – esse recurso estende a estrutura de integração fiscal adicionando a possibilidade de criar conectores fiscais que serão executados no PDV (ponto de venda). Esse tipo de conector se comunica com um dispositivo ou serviço fiscal que fornece uma API (interface de programação de aplicativo) HTTP e não requer uma máquina física dedicada na loja. Por exemplo, essa funcionalidade permite a integração fiscal para dispositivos móveis sem a necessidade de estação de hardware compartilhada.
    - **Substituições do perfil técnico de integração fiscal** – esse recurso permite que a configuração da integração fiscal seja expandida e adiciona a possibilidade de substituir os parâmetros de um perfil técnico. Por exemplo, é possível especificar cadeias de conexão do dispositivo fiscal no nível do terminal de PDV individual. O recurso também adiciona a possibilidade de verificar os parâmetros de conexão na página **Configurações** de um terminal de PDV. 
    - **Estado do Registro Fiscal de Terminais de PDV** – quando esse recurso é habilitado, é possível desabilitar o processo de registro fiscal de terminais de PDV específicos. Se o registro fiscal estiver desabilitado para um terminal de PDV, as transações de vendas não poderão ser concluídas nesse terminal.
    - **Backup de armazenamento local de integração fiscal** – esse recurso amplia os recursos de tratamento de erros da estrutura de integração fiscal permitindo o backup automático dos dados de registro fiscal de modo que a restauração desses dados no armazenamento local possam ser restaurados enquanto um dispositivo esteja sendo ativado.
    - **Registro adiado de documentos** – esse recurso estende os recursos de tratamento de erros da estrutura de integração fiscal habilitando a opção de adiar o registro fiscal no caso de uma falha de registro fiscal e usar uma opção de registro fiscal de backup ou concluir o registro fiscal posteriormente por meio de uma estrutura de integração fiscal.

## <a name="set-up-commerce-parameters"></a>Configurar parâmetros do Commerce

Para configurar os parâmetros do Commerce, siga as etapas:

1. Na página **Parâmetros compartilhados do Commerce**, na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**.
1. Na guia **Sequências numéricas**, defina as sequências numéricas para as seguintes referências:

    - Número do perfil técnico fiscal
    - Número do grupo do conector fiscal
    - Número do processo de registro

1. Na página **Parâmetros do Commerce**, defina a sequência numérica para o número do perfil funcional fiscal.

> [!NOTE]
> Sequências numéricas são opcionais. Os números de todas as entidades de integração fiscal podem ser gerados a partir de sequências numéricas ou manualmente.

## <a name="set-up-a-fiscal-registration-process"></a>Configurar um processo de registro fiscal

O processo de configuração da integração fiscal inclui as seguintes tarefas:

- Configure conectores fiscais que representam dispositivos ou serviços fiscais usados para fins de registro fiscal, como impressoras fiscais.
- Configure provedores de documentos que geram documentos fiscais que serão registrados em dispositivos ou serviços fiscais por conectores fiscais.
- Configure o processo de registro fiscal que define uma sequência de etapas de registro fiscal e os conectores fiscais e provedores de documentos fiscais usados para cada etapa.
- Atribua o processo de registro fiscal a perfis de funcionalidade de PDV.
- Atribua perfis técnicos de conectores a perfis de hardware.
- Atribua perfis técnicos de conectores a perfis de hardware ou funcionalidade de PDV.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Carregue configurações de provedores de documentos fiscais

Um provedor de documentos fiscais é responsável por gerar documentos fiscais que representam transações e eventos registrados no PDV em um formato que também é usado para a interação com um dispositivo ou serviço fiscal. Por exemplo, um provedor de documentos fiscais pode gerar uma representação de um recibo fiscal em um formato XML.

Para carregar configurações de provedores de documentos fiscais, siga estas etapas.

1. No Commerce headquarters, vá para a página **Provedores de documentos fiscais** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Provedores de documento fiscal**).
1. Carregue uma configuração XML para cada dispositivo ou serviço que você pretende usar.

> [!TIP]
> Selecionando **Exibir**, é possível exibir todos os perfis funcionais relacionados ao provedor de documentos fiscais atual.

> [!NOTE]
> O mapeamento de dados é considerado uma parte do provedor de documentos fiscais. Para configurar diferentes mapeamentos de dados para o mesmo conector (por exemplo, regulamentações específicas de estado), crie diferentes provedores de documentos fiscais.

### <a name="upload-configurations-of-fiscal-connectors"></a>Carregar configurações de conectores fiscais

Um conector fiscal é responsável pela comunicação com um dispositivo ou serviço fiscal. Por exemplo, um conector fiscal pode enviar um recibo fiscal que um provedor de documentos fiscais criou em um formato XML para uma impressora fiscal. Para obter mais detalhes sobre componentes de integração fiscal, consulte [Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais e serviços](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Para carregar configurações de conectores fiscais, siga estas etapas.

1. No Commerce headquarters, vá para a página **Conectores fiscais** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Conectores fiscais**).
1. Carregue uma configuração XML para cada dispositivo ou serviço que você pretende usar para fins de integração fiscal.

> [!TIP]
> Selecionando **Exibir**, é possível exibir todos os perfis funcionais e técnicos relacionados ao conector fiscal atual.

Para obter exemplos de configurações de conectores fiscais e provedores de documentos fiscais, consulte [Exemplos de integração fiscal no SDK do Commerce](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Crie perfis funcionais do conector

Para criar perfis funcionais do conector, siga estas etapas.

1. No Commerce headquarters, vá para a página **Perfis funcionais do conector** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Conectores fiscais**).
1. Para cada combinação de um conector fiscal e um provedor de documentos fiscais que está relacionada a este conector fiscal, crie um perfil funcional de conector seguindo estas etapas:

    1. Selecione um nome de conector.
    1. Selecione um provedor de documento.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Altere os parâmetros de mapeamento de dados em um perfil funcional do conector

É possível alterar os parâmetros de mapeamento de dados em um perfil funcional do conector. A tabela a seguir fornece exemplos de parâmetros de mapeamento de dados em um perfil funcional do conector.

| Parâmetro | Formatar | Exemplo |
|-----------|--------|---------|
| Configurações de alíquotas de IVA | valor: VATrate | 1 : 2000, 2 : 1800 |
| Mapeamento dos códigos IVA | VATcode : valor | vat20 : 1, vat18 : 2 |
| Mapeamento de tipos de meio de pagamento | TenderType : valor | Caixa: 1, cartão: 2 |

Para restaurar os parâmetros padrão definidos na configuração do provedor de documentos fiscais, selecione **Atualizar** na página **Perfis funcionais do conector**.

> [!NOTE]
> Os perfis funcionais do conector são específicos da empresa. Se você planeja usar a mesma combinação de um conector fiscal e um provedor de documentos fiscais para empresas diferentes, crie um perfil funcional de conector para cada empresa.

### <a name="create-connector-technical-profiles"></a>Crie perfis técnicos do conector

Para criar perfis técnicos do conector, siga estas etapas.

1. No Commerce headquarters, vá para a página **Perfis técnicos do conector** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**).
1. Criar um perfil técnico de conector para cada conector fiscal, seguindo estas etapas:

    1. Selecione um nome de conector.
    1. Selecione um tipo de conector:

        - Para dispositivos ou serviços conectados a uma estação de hardware ou presente na rede local, selecione **Local**.
        - Para serviços externos, selecione **Externo**.
        - Para conectores internos no Commerce Runtime (CRT), selecione **Interno**. 

    1. Selecione um local do conector:

        - Se o conector estiver localizado na estação de hardware, selecione **Estação de hardware**.
        - Se o conector estiver localizado no terminal de PDV, selecione **Terminal**.

Parâmetros nas guias **Dispositivo** e **Configurações** em um perfil técnico do conector podem ser alterados. Para restaurar os parâmetros padrão definidos na configuração do conector fiscal, selecione **Atualizar**. Enquanto uma nova versão de uma configuração XML é carregada, você receberá uma mensagem informando que o conector fiscal atual ou o provedor de documentos fiscais já está sendo usado. Esse procedimento não substitui alterações manuais que foram feitas anteriormente em perfis funcionais de conectores e perfis técnicos de conectores. Para aplicar o conjunto padrão de parâmetros de uma nova configuração, selecione **Atualizar** na página **Perfis funcionais do conector** ou a página **Perfis técnicos do conector**.

Se você tiver que configurar parâmetros específicos para um armazenamento ou terminal de PDV individual, siga estas etapas.

1. Selecione o item de menu **Substituir**.
1. Na página **Substituir**, crie um novo registro.
1. Selecione uma loja ou um terminal de PDV. Você pode substituir parâmetros do perfil técnico selecionado para um terminal de PDV individual ou todos os terminais de PDV em um armazenamento individual.
1. Na guia **Dispositivo**, insira os parâmetros do armazenamento ou do terminal de PDV selecionado.

### <a name="create-fiscal-connector-groups"></a>Crie grupos de conectores fiscais

Um grupo de conectores fiscais combina perfis funcionais de conectores fiscais que executam funções idênticas e são usados na mesma etapa de um processo de registro fiscal. Por exemplo, se vários modelos de impressoras fiscais puderem ser usados em uma loja, os conectores fiscais dessas impressoras fiscais poderão ser combinados em um grupo de conectores fiscais.

Para criar um grupo de conectores fiscais, siga estas etapas.

1. Vá até a página **Grupo do conector fiscal** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Grupos do conector fiscal**).
1. Crie um novo grupo de conectores fiscais.
1. Adicione perfis funcionais ao grupo de conectores. Na guia **Perfis funcionais**, selecione **Adicionar** e selecione um número do perfil. Cada conector fiscal em um grupo de conectores só pode ter um perfil funcional.
1. Para suspender o uso do perfil funcional, defina a opção **Desabilitar** como **Sim**. Essa alteração só afeta o grupo de conectores atual. Você pode continuar usando o mesmo perfil funcional em outros grupos de conectores.

### <a name="create-a-fiscal-registration-process"></a>Crie um processo de registro fiscal

Um processo de registro fiscal é definido pela sequência de etapas de registro e pelo grupo de conectores usado para cada etapa.

Para criar um processo de registro fiscal, siga estas etapas.

1. No Commerce headquarters, vá para a página **Processo de registro fiscal** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**).
1. Crie um novo registro para cada processo de registro fiscal exclusivo.
1. Para adicionar etapas de registro ao processo, siga estas etapas:

    1. Selecione **Adicionar**.
    1. Selecione um tipo de conector fiscal.
    1. No campo **Número do grupo**, selecione um grupo de conectores fiscais apropriado.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Atribua entidades do processo de registro fiscal a perfis de PDV

Para atribuir entidades do processo de registro fiscal a perfis de PDV, siga estas etapas.

1. No Commerce headquarters, vá para a página **Perfis de funcionalidade de PDV** (**Varejo e Comércio \> Configuração do canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**). 
1. Atribua o processo de registro fiscal a um perfil de funcionalidade de PDV.
1. Selecione **Editar** e, na guia **Processo de registro fiscal**, no campo **Número do processo**, selecione um processo.
1. Na guia **Serviços fiscais**, selecione perfis técnicos de conector com o **Registro** de local do conector.
1. Vá até a página **Perfil de hardware do PDV** (**Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfil de hardware**).
1. Atribua perfis técnicos de conectores a um perfil de hardware. 
1. Selecione **Editar** e, na guia **Periféricos fiscais**, adicione uma linha. 
1. No campo **Número de perfil**, selecione um perfil técnico do conector.
1. Na guia **Periféricos fiscais**, selecione perfis técnicos de conector com a **Estação de hardware** de local do conector.

> [!NOTE]
> Você pode adicionar vários perfis técnicos ao mesmo perfil de hardware. No entanto, um perfil de hardware ou um perfil de funcionalidade de PDV deve ter apenas uma interseção com qualquer grupo de conectores fiscais.

O fluxo de registro fiscal é definido pelo processo de registro fiscal e também por alguns parâmetros de componentes de integração fiscal: a extensão do CRT para o provedor de documentos fiscais e a extensão da estação de hardware para o conector fiscal.

- A inscrição de eventos e transações no registro fiscal é predefinida no provedor de documentos fiscais.
- O provedor de documentos fiscais também é responsável por identificar o conector fiscal usado para o registro fiscal. Ele corresponde aos perfis funcionais do conector que estão incluídos no grupo de conectores fiscais especificado para a etapa atual do processo de registro fiscal com o perfil técnico do conector que é atribuído ao perfil de hardware da estação de hardware ao qual o PDV está emparelhado.
- O provedor de documentos fiscais usa as configurações de mapeamento de dados da configuração do provedor de documento fiscal para transformar dados de transação/evento, como impostos e pagamentos, enquanto um documento fiscal é gerado.
- Quando o provedor de documentos fiscais gera um documento fiscal, o conector fiscal pode enviá-lo para o dispositivo fiscal no estado em que se encontra ou analisá-lo e transformá-lo em uma sequência de comandos da API do dispositivo, dependendo de como a comunicação é tratada.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Configurar registros com restrições de registro fiscal

Você pode selecionar registros em que registros fiscais são proibidos; por exemplo, em casos onde você precisa fornecer somente operações não fiscais, como pesquisa de catálogo de produtos, pesquisa de cliente ou criação de rascunho de transação nesses dispositivos.

Para configurar registros com restrições de registro fiscal, siga estas etapas.

1. No Commerce headquarters, vá para **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**.
1. Selecione o processo obrigatório.
1. Selecione a guia **Terminais de PDV com restrições de processo fiscal**.
1. Adicione registros com restrições de processo fiscal, conforme necessário.

### <a name="validate-the-fiscal-registration-process"></a>Valide o processo de registro fiscal

É recomendável que você valide o processo de registro fiscal nos seguintes casos:

- Você concluiu todas as configurações de um novo processo de registro. Essas configurações incluem a atribuição de processos de registro aos perfis de funcionalidade de PDV e de hardware.
- Você fez alterações em um processo de registro fiscal existente e essas alterações podem fazer com que um conector fiscal diferente seja selecionado no tempo de execução. (Por exemplo, você alterou o grupo de conectores para uma etapa do processo de registro fiscal, ativou um perfil funcional de conector em um grupo de conectores ou adicionou um novo perfil funcional de conector a um grupo de conectores.)
- Você fez alterações na atribuição de perfis técnicos de conectores a perfis de hardware.

Para validar o processo de registro fiscal, siga estas etapas.

1. No Commerce headquarters, vá para a página **Processo de registro fiscal** (**Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**).
1. Selecione **Validar** para validar o processo de registro fiscal.
1. Na página **Agenda de distribuição**, execute os trabalhos **1070** e **1090** para transferir dados para o banco de dados do canal.

## <a name="set-up-fiscal-texts-for-discounts"></a>Configurar textos fiscais para descontos

Em alguns casos, um texto especial deve ser impresso em um recibo fiscal se um desconto for aplicado. Você pode configurar textos fiscais para descontos na página **Grupo do conector fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Grupos do conector fiscal**).

- Para descontos manuais aplicados no PDV, defina um texto fiscal para o código de informação ou o grupo de códigos de informação especificado como o código de informação do **Desconto de produto** no perfil de funcionalidade do PDV.

    1. Na página **Grupo do conector fiscal**, selecione **Texto do recibo fiscal**.
    1. Na guia **Códigos de informação**, selecione **Adicionar** e selecione um código de informação ou um grupo de códigos de informação.
    1. No campo **Número do código de informação**, selecione um valor.
    1. No campo **Número de subcódigo**, selecione um valor se for necessário um subcódigo para o código de informação selecionado.
    1. No campo **Texto do recibo fiscal**, especifique um texto fiscal que deve ser impresso em um recibo fiscal.
    1. Defina a opção **Imprimir entrada de usuário no recibo fiscal** como **Sim** para substituir o texto em um recibo fiscal com informações que um usuário insere manualmente no PDV. Essa opção aplica-se apenas aos códigos de informação que possuem um tipo de entrada de **Texto**.

    > [!NOTE]
    > Você pode especificar um texto fiscal para vários códigos de informação para dar suporte a cenários em que grupos de códigos de informação, códigos de informação vinculados e códigos de informação acionados são usados. Nesses cenários, o recibo fiscal conterá os textos fiscais de todos os códigos de informação vinculados à linha de transação na qual o desconto foi aplicado.

- Para descontos específicos do canal, você deve definir um texto fiscal para o código de desconto.

    1. Na página **Grupo do conector fiscal**, selecione **Texto do recibo fiscal**.
    1. Na guia **Descontos**, selecione **Adicionar** e selecione uma ID do desconto.
    1. No campo **Texto do recibo fiscal**, especifique um texto fiscal que deve ser impresso em um recibo fiscal.

    > [!NOTE]
    > Se vários descontos forem aplicados à mesma linha de transação, o recibo fiscal conterá textos fiscais de todos os descontos vinculados a essa linha de transação.

## <a name="set-error-handling-settings"></a>Definir configurações de tratamento de erros

As opções de tratamento de erros disponíveis na integração fiscal são definidas no processo de registro fiscal. Para obter mais informações sobre o tratamento de erros na integração fiscal, consulte [Tratamento de erro](fiscal-integration-for-retail-channel.md#error-handling).

Para definir as configurações de tratamento de erros, siga estas etapas.

1. Na página **Processo de registro fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Processos de registros fiscais**), você pode definir os parâmetros a seguir para cada etapa do processo de registro fiscal:

    - **Permitir ignorar** – Este parâmetro habilita a opção **Ignorar** na caixa de diálogo de tratamento de erros.
    - **Permitir marcar como registrado** – Este parâmetro habilita a opção **Marcar como registrado** na caixa de diálogo de tratamento de erros.
    - **Permitir adiamento** – Este parâmetro habilita a opção **Adiar** na caixa de diálogo de tratamento de erros.
    - **Continuar se houver erro** – Se este parâmetro estiver habilitado, o processo de registro fiscal poderá continuar no terminal de PDV em caso de falha no registro de uma transação ou de um evento. Do contrário, para executar o registro fiscal da próxima transação ou evento, o operador deve repetir o registro fiscal com falha, ignorá-lo ou marcar a transação ou ao evento como registrados. Para obter mais informações, consulte [Registro fiscal opcional](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Se o parâmetro **Continuar se houver erro** for habilitado, os parâmetros **Permitir ignorar** e **Permitir marcar como registrado** serão desabilitados automaticamente.

1. As opções **Ignorar** e **Marcar como registrado** na caixa de diálogo de tratamento de erros exigem que a permissão **Permitir ignorar o registro ou marcar como registrado** seja habilitada. Para habilitar esta permissão, vá para a página **Grupos de permissão** (**Varejo e Comércio \> Funcionários \> Grupos de permissão**) e defina a opção **Permitir ignorar o registro ou marcar como registrado** como **Sim**.
1. A opção **Adiar** na caixa de diálogo de tratamento de erros requer que a permissão **Permitir adiantamento** seja habilitada. Para habilitar a permissão, vá para a página **Grupos de permissão** (**Varejo e Comércio \> Funcionários \> Grupos de permissão**) e defina a opção **Permitir adiamento** como **Sim**.
1. As opções **Ignorar**, **Marcar como registrado** e **Adiar** permitem que os operadores insiram informações adicionais quando o registro fiscal falha. Para disponibilizar essa funcionalidade, você deve especificar os códigos de informações **Ignorar**, **Marcar como registrado** e **Adiar** em um grupo de conectores fiscais. As informações inseridas pelos operadores são salvas como uma transação de código de informação vinculada à transação fiscal. Para obter mais detalhes sobre códigos de informação, consulte [Códigos informativos e grupos de códigos informativos](../info-codes-retail.md).

    > [!NOTE]
    > A função do disparador **Produto** não é compatível com os códigos de informação que são usados para **Ignorar** e **Marcar como registrado** em grupos de conectores fiscais.

    - Na página **Grupo do conector fiscal**, na guia **Códigos de informação** selecione códigos de informação ou grupos de códigos de informação nos campos **Ignorar**, **Marcar como registrado** e **Adiar**.

    > [!NOTE]
    > Um documento fiscal e um documento não fiscal podem ser gerados em qualquer etapa de um processo de registro fiscal. Uma extensão de provedor de documentos fiscais identifica cada tipo de transação ou evento como relacionado a documentos fiscais ou não fiscais. O recurso de tratamento de erros aplica-se apenas a documentos fiscais.
    >
    > - **Nota fiscal** – Um documento obrigatório que deve ser registrado com sucesso (por exemplo, um recibo fiscal).
    > - **Documento não fiscal** – Um documento suplementar para a transação ou evento (por exemplo, um comprovante de cartão de presente).

1. Se o operador deve poder continuar a processar a operação atual (por exemplo, criar ou finalizar uma transação) após um erro de verificação de integridade, você deve habilitar a permissão **Permitir ignorar o erro de verificação de integridade** na página **Grupos de permissões** (**Retail e Commerce \> Funcionários \> Grupos de permissões**). Para obter mais informações sobre o procedimento de verificação de integridade, consulte [Verificação de integridade do registro fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configurar relatórios fiscais X/Z a partir do PDV

Para permitir que os relatórios fiscais X/Z sejam executados a partir do PDV, você deve adicionar novos botões a um layout de PDV.

- Na página **Grades de botões**, siga as instruções em [Adicionar operações de PDV a layouts de PDV usando um Designer de grade de botões](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar o designer e atualizar um layout de PDV.

    1. Selecione o layout para atualizar. 
    1. Adicione um novo botão e defina a propriedade do botão **Leitura X**.
    1. Adicione um novo botão e defina a propriedade do botão **Redução Z**.
    1. Na página **Agenda de distribuição**, execute o trabalho **1090** para transferir as alterações para o banco de dados do canal.

## <a name="enable-manual-execution-of-deferred-fiscal-registration"></a>Habilitar a execução manual do registro fiscal adiado

Para habilitar a execução manual de um registro fiscal adiado, você deve adicionar um novo botão a um layout do PDV.

- Na página **Grades de botões**, siga as instruções em [Adicionar operações de PDV a layouts de PDV usando um Designer de grade de botões](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar o designer e atualizar um layout de PDV.

    1. Selecione o layout para atualizar.
    1. Adicione um novo botão e defina a propriedade do botão **Concluir processo de registro fiscal**.
    1. Na página **Agenda de distribuição**, execute o trabalho **1090** para transferir suas alterações para o banco de dados do canal.

## <a name="view-connection-parameters-and-other-information-in-pos"></a>Exibir parâmetros de conexão e outras informações no PDV

Para exibir os parâmetros de conexão e outras informações no PDV, siga estas etapas:

1. Abra o Modern POS (MPOS) ou o PDV em Nuvem (CPOS).
1. Selecione **Configurações**. Se a integração fiscal estiver habilitada, a seção **Integração fiscal** à direita mostrará as seguintes informações:

    - O status do registro fiscal
    - O estado da última transação fiscal
    - O número de eventos de auditoria pendentes

1. Selecione **Detalhes** para exibir as seguintes informações:

    - Etapas do processo de registro
    - Parâmetros de conexão
    - Detalhes dos eventos de auditoria
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
