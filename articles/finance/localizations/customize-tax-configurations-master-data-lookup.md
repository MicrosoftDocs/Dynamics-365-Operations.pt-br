---
title: Personalizar configurações de imposto para pesquisa de dados mestres
description: Este tópico explica como personalizar as configurações de imposto para estender a funcionalidade de pesquisa de dados mestres.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 498201d5c0377058e86b25953ebbe401ae1af9e3
ms.sourcegitcommit: ed43ceae9b2ef3f616b81127bcf4c4b0862e23f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2021
ms.locfileid: "7714871"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Personalizar configurações de imposto para pesquisa de dados mestres

[!include [banner](../includes/banner.md)]

Siga as etapas neste tópico para personalizar as configurações de imposto para estender a funcionalidade de pesquisa de dados mestres.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Importar uma configuração de imposto fornecida pela Microsoft

1. No Regulatory Configuration Service (RCS), no espaço de trabalho **Relatório eletrônico**, selecione o provedor de configuração da **Microsoft**.
2. Selecione **Repositórios**.
3. Selecione **Global** e, em seguida, selecione **Abrir**.
4. Selecione uma configuração de imposto, como **Configuração de Cálculo de Imposto** e, na guia **Versões**, selecione uma versão.
5. Selecione **Importar**.

> [!NOTE]
> Por padrão, o mapeamento de modelos do Dataverse é importado. Se você receber mensagens de aviso durante o processo de importação da configuração, habilite as entidades virtuais no Dataverse. Para obter mais informações, consulte [Habilitar entidades virtuais do Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Criar uma configuração personalizada de modelo de dados

1. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de imposto** e, em seguida, selecione a configuração do modelo de dados a ser estendida. Por exemplo, selecione **Modelo de dados de Cálculo de Imposto**.
2. Selecione **Criar configuração**.
3. Selecione o **Modelo de documento tributável derivado de Nome: modelo de dados de imposto, Microsoft**.
4. No campo **Nome**, insira **Modelo de dados de personalização**.
5. Selecione **Criar configuração**.

## <a name="create-customized-reference-models"></a>Criar modelos de referência personalizados

1. Na página **Configurações de imposto**, selecione **Modelo de dados de personalização** e, em seguida, selecione **Designer**.
2. Selecione o botão de reticências (**...**) e, em seguida, selecione a exibição **Modelo de referência**.

    [![Modelo de referência.](./media/pic2.png)](./media/pic2.png)

3. Crie o modelo de referência personalizado. O modelo personalizado é um modelo raiz. A entidade personalizada é uma lista de registros. O campo personalizado é um campo de cadeia de caracteres que você deseja usar na pesquisa. É possível adicionar mais campos conforme necessário.
4. Selecione o botão de reticências (**...**) e, em seguida, selecione a exibição **Documento tributável**.
5. Selecione o atributo a ser vinculado ao modelo de referência personalizado. Por exemplo, selecione **Atributo personalizado** e siga estas etapas:

    1. Selecione **Selecionar modelo de referência**.
    2. Selecione **Modelo personalizado** e, em seguida, selecione **OK**. O nome do modelo de referência é atualizado para o valor do campo **Chave natural**.

        [![Selecione a caixa de diálogo do modelo de referência.](./media/pic5.png)](./media/pic5.png)

    3. Selecione **Salvar** e **Concluído**.

## <a name="create-a-customized-model-mapping-configuration"></a>Criar uma configuração personalizada de mapeamento de modelos

1. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de imposto** e, em seguida, selecione a configuração do **mapeamento de modelos do Dataverse**.
2. No campo **Padrão do mapeamento de modelos**, selecione **Não**.
3. Selecione **Criar configuração**.
4. Selecione **Mapeamento de modelos de documento tributável derivado de Nome: mapeamento de modelo do Dataverse, Microsoft**.
5. No campo **Nome**, insira **Mapeamento de modelo de personalização**.
6. No campo **Modelo de destino**, selecione o modelo de dados **Modelo de dados de personalização**.
7. Selecione **Criar configuração**.

    [![Caixa de diálogo suspensa Criar configuração.](./media/pic6.png)](./media/pic6.png)

8. Selecione **Mapeamento de modelos de personalização** e defina o campo **Aplicativo conectado** como a conexão criada na etapa 8, em [Configurar um ambiente para pesquisa de dados mestres](tax-service-set-up-environment-master-data-lookup.md).
9. Defina o campo **Padrão do mapeamento de modelos** como **Sim**.

## <a name="create-customized-model-mappings"></a>Criar mapeamentos de modelos personalizados

1. Na página **Configurações de imposto**, selecione **Mapeamento de modelos de personalização**.
2. Selecione **Designer** e, em seguida, selecione **Modelo de personalização**.

    [![Modelo de personalização.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Mapear um mapeamento de modelos para uma entidade do Dataverse

1. Na página **Designer de mapeamento de modelos**, selecione **Modelo de personalização** e, em seguida, selecione **Designer**.
2. No painel **Tipos de fonte de dados**, selecione **Tabela do Dataverse**.
3. Na guia **Fontes de dados**, selecione **Adicionar raiz**.
4. No campo **Nome**, insira **Dataverse Personalizado**.
5. No segundo campo **Nome**, selecione uma entidade.
6. Selecione **OK**.

    [![Caixa de diálogo de propriedades da fonte de dados da Tabela.](./media/pic9.png)](./media/pic9.png)

7. Selecione **Dataverse Personalizado** e **Entidade personalizada** e, em seguida, selecione **Associar**.

    [![Associação do Dataverse Personalizado e da entidade personalizada.](./media/pic10.png)](./media/pic10.png)

8. Em **Dataverse Personalizado** e no **Campo personalizado**, selecione um campo e, em seguida, selecione **Associar**.

    [![Associação do Dataverse Personalizado e do Campo personalizado.](./media/pic11.png)](./media/pic11.png)

9. Selecione **Salvar** e **Concluído**.

## <a name="create-a-customized-tax-configuration"></a>Criar uma configuração personalizada de imposto

1. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de imposto** e, em seguida, selecione **Configuração do Cálculo de Imposto**.
2. Selecione **Criar configuração**.
3. Selecione **Configuração de serviço de impostos derivada de Nome: Configuração de Cálculo de Imposto, Microsoft**.
4. No campo **Nome**, insira **Configuração de personalização**.
5. Selecione **Criar configuração**.
6. Selecione **Configuração de personalização** e, em seguida, selecione **Designer**.
7. No campo **Modelo de dados**, selecione **Modelo de dados de personalização**.
8. No campo **Versão do modelo de dados**, selecione a versão do modelo de dados correspondente.

    [![Seção Propriedades.](./media/pic13.png)](./media/pic13.png)

9. Selecione **Concluir**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
