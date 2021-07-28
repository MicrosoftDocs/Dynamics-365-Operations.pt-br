---
title: Definir mensagens eletrônicas para eventos do SPED-Reinf
description: Este tópico explica como configurar mensagens eletrônicas para eventos SPED-Reinf para o Brasil.
author: sndray
ms.date: 04/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 2db0347b9da164b122082f26b668d681894e2241
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359235"
---
# <a name="set-up-electronic-messages-for-sped-reinf-events"></a>Definir mensagens eletrônicas para eventos do SPED-Reinf

A funcionalidade de mensagens eletrônicas é nova no Microsoft Dynamics 365 Finance. Ela permite manter e acompanhar vários processos de mensagens eletrônicas quando há uma troca de informações entre o Finance e os serviços Web da autoridade fiscal.

Antes de emitir eventos SPED-Reinf para o site do governo, use a configuração predefinida que a Microsoft preparou para atender aos requisitos SPED-Reinf. Essa configuração é fornecida como uma entidade de dados. Quando ele for importado para o Finance, os usuários poderão gerar, validar e fornecer todos os eventos que são descritos no escopo do SPED-Reinf.

## <a name="import-the-configuration-from-the-data-entity"></a>Importar a configuração da entidade de dados

Para configurar a funcionalidade de mensagem eletrônica para a comunicação de eventos do SPED-Reinf, use a configuração predefinida disponível no Microsoft Dynamics Lifecycle Services (LCS).

1. Entre no [LCS](https://lcs.dynamics.com).
2. Selecione o bloco **Biblioteca compartilhada de ativos**.
3. Selecione **Pacote de dados** como o tipo de ativo e selecione o pacote para as entidades de dados de comunicação do evento do SPED-Reinf. (O nome do arquivo é **SPEDReinf_EMSettings.zip**.)
4. Salve o arquivo no local em que as entidades de dados devem ser armazenadas.
5. Entre no Finance e vá para **Espaços de trabalho** \> **Gerenciamento de dados**.
6. Selecione o bloco **Importação**.
7. Insira uma descrição e um nome para identificar o trabalho, como **SpedReinf**.
8. No campo **Formato de dados de origem**, selecione **Pacote**.
9. Selecione **Carregar** e, em seguida, selecione o arquivo que você salvou do LCS (**SPEDReinf_EMSettings.zip**).
10. Selecione **Salvar** e aguarde até que todas as entidades de dados sejam mostradas na página.
11. Selecione **Importar**.

    Você receberá uma notificação sobre o processo de importação. Você também pode atualizar a página manualmente para visualizar o progresso do processo de importação. Quando o processo for concluído, você poderá visualizar a página **Resumo de execução**.

    ![Página Resumo de execução.](media/bra-execution-summary-page.png)

## <a name="structure-of-electronic-messages"></a>Estrutura de mensagens eletrônicas

Cada evento criado, entregue e recebido é representado por uma mensagem e um item de mensagem.

![Estrutura de mensagens eletrônicas.](media/bra-electronic-messages-structure.png)

O item de mensagem é representado pela mensagem do evento XLM. Isso inclui as seguintes informações que são armazenadas na mensagem ou atualizada no Finance:

- O número completo do CNPJ (Cadastro Nacional de Pessoas Jurídicas) do estabelecimento fiscal
- O CNPJ raiz
- O período de escrituração
- A data inicial do período para o qual a mensagem é válida
- O número do protocolo de recebimento
- Um valor que indica se a mensagem está registrada no Dynamics 365

Você pode encontrar esta configuração na página **Campos adicionais** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Campos adicionais**).

![Configuração na página Campos adicionais.](media/bra-electronic-messaging-additional-fields.png)

> [!NOTE]
> Não remova esta configuração. Essa configuração está incluída no pacote.

Os tipos de item de mensagem são classificados pelo tipo de evento na página **Tipos de item de mensagem** (**Imposto** \> **Configuração** \> **Mensagem eletrônica** \> **Tipos de item de mensagem**).

![Página Tipos de item de mensagem.](media/bra-message-types.png)

> [!NOTE]
> Não remova esta configuração. Essa configuração está incluída no pacote.

- Para configurar a sequência numérica para itens de mensagem, acesse **Imposto \> Configuração \> Parâmetros \> Parâmetros do razão geral** e, na guia **Sequências numéricas**, selecione uma sequência numérica para as referências **Mensagem** e **Item de mensagem**.

![Guia Sequências numéricas na página Parâmetros do razão geral.](media/bra-electronic-messages-number-sequences.png)

> [!NOTE]
> A sequência numérica deve ser definida como não contínua.

## <a name="certificates"></a>Certificados

Os certificados confiáveis devem ser configurados e usados no Finance, pois o SPED-Reinf deve sempre ser assinado por um certificado de e-CNPJ que seja autorizado pela Infraestrutura de Chave Pública do Brasil (ICP-Brasil), independentemente de outras assinaturas. Este certificado de e-CNPJ deve corresponder aos oito primeiros dígitos do número de CNPJ do estabelecimento fiscal raiz, pois o relatório é emitido pelo estabelecimento fiscal raiz e os estabelecimentos fiscais relacionados.

No Finance, você deve registrar o certificado do Key Vault no Azure.

Para obter informações sobre como configurar um cliente do Key Vault, consulte [Configuração do Cliente do Azure Key Vault](https://support.microsoft.com/help/4040305).

1. Vá para **Administração do sistema** \> **Configuração** \> **Parâmetros do Key Vault**.
2. Digite as seguintes informações:

    - URL do Key Vault
    - Cliente do Key Vault
    - Chave secreta do Key Vault
    - ID secreto do Key Vault

Após o registro, associe o certificado nos parâmetros de configuração para a ação **Geração de relatório**, conforme descrito na seção a seguir.

## <a name="set-up-parameters"></a>Configurar parâmetros 

Sempre que uma mensagem é criada, preparada, validada, entregue ou recebida, a ação relacionada deve ser identificada por meio de uma classe X++ na página **Configurações de classe executável** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de classe executável**).

- **Preparação dos eventos –** Esta ação é usada para criar e preparar a mensagem XML. Esta ação solicita mais parâmetros, tais como **Data da reserva**, **CNPJ** e **CNPJ raiz**, pois os eventos são gerados com base nessas informações.

    ![Parâmetros de itens de preparação.](media/bra-preparation-items.png)

- **Resposta do processo** - Esta ação é usada para atualizar a mensagem entregue quando o governo a aprova usando um número de protocolo. Além disso, a mensagem é atualizada como registrada no site do governo.

    ![Parâmetros de resposta do processo de itens de preparação.](media/bra-preparation-items-process-response.png)

- **Geração de relatório** – Esta ação é usada para enviar e receber o item de mensagem.

    ![Gerar parâmetros de relatórios.](media/bra-generate-reports-parameters.png)

> [!NOTE]
> Não remova esta configuração. Essa configuração está incluída no pacote.

## <a name="specific-actions"></a>Ações específicas

Antes de uma mensagem ser entregue, configure a validação do esquema XML para ajudar a evitar rejeições por parte do site do governo.

1. Vá para **Administração da organização** \> **Gerenciamento de documentos** \> **Parâmetros de gerenciamento de documentos** e habilite arquivos .xsd adicionando **XSD** como um novo tipo de arquivo.

    ![Página Parâmetros de gerenciamento de documentos.](media/bra-document-management-parameters.png)

2. Vá para **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagem** e selecione **Novo** \> **Arquivo** para anexar os esquemas (arquivos .xsd) às seguintes ações:

    - Validar
    - Re-Validar
    - Exclusão-Validar

3. Vá para **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagem**, selecione a ação **Preencher** (**Incluir**) e, no campo **Preencher ação de registro**, selecione **Registrar transacões**.

    ![Página Ações de processamento de mensagem.](media/bra-message-processing-actions.png)

4. Vá para **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de serviços Web** e configure uma conexão de serviços Web e certificados para emitir e consultar eventos.

    ![Página Configurações de serviços Web.](media/bra-web-service-settings.png)

> [!NOTE]
> Nas configurações do **SPED Reinf assíncrono**, inclua o endereço do serviço Web para consultar o evento R-5011.
