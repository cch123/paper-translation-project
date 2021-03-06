# What Serverless Computing Is and Should Become: The Next Phase of Cloud Computing

original : [serverless](https://cacm.acm.org/magazines/2021/5/252179-what-serverless-computing-is-and-should-become/fulltext)

2010年，我们中的一些人共同撰写了一篇《通信》文章，帮助解释云计算这一相对较新的现象。4 我们说，云计算提供了无限扩展的远程服务器的幻觉，而没有收取规模费用，因为租用1000台服务器一小时的费用与租用一台服务器1000小时的费用相同，而且云计算供应商的规模经济使其价格出奇的便宜。我们列举了云计算的挑战，然后预测大多数挑战将被克服，因此该行业将越来越多地从本地数据中心内的计算转移到 "云"，而这确实已经发生。今天，三分之二的企业在基础设施和软件方面的信息技术支出是基于云的。

我们在十年后重新审视云计算，以解释其正在出现的第二阶段，我们相信这将进一步加速向云计算的转变。第一阶段主要是简化系统管理，使配置和管理计算基础设施更加容易，主要是通过使用从大规模多租户数据中心划分出来的虚拟服务器和网络。第二阶段通过为应用建设者提供简化云计算开发的编程抽象来隐藏服务器，使云计算软件更容易编写。简单地说，第一阶段的目标是系统管理员，第二阶段是程序员。这种变化要求云供应商接管许多运行应用程序所需的操作责任。

为了强调重点从服务器到应用程序的变化，这个新阶段已被称为无服务器计算，尽管远程服务器仍然是为其提供动力的无形基石。在本文中，我们称传统的第一阶段为有服务器计算。

图1显示了一个比喻。为了参加一个远程会议，你要么租一辆车，要么叫一辆出租车，从机场到酒店。租车就像是有服务器的计算，你必须排队等候，签署合同，无论你如何使用，都要为整个逗留期间保留汽车，自己开车，导航到酒店，支付停车费，并在还车前加满油。出租车就像无服务器计算，你只需要提供酒店名称和支付车费；出租车服务提供训练有素的司机，为你导航，收取车费，并为油箱加油。出租车简化了交通，因为你不需要知道如何操作汽车就能到达酒店。此外，出租车的利用率比租车高，这也降低了出租车公司的成本。根据会议的长度，租车的费用，停车的费用，汽油的费用等等，出租车不仅更容易，甚至可能更便宜。

![](https://dl.acm.org/cms/attachment/d7c7af17-b8eb-4da0-b976-e2f1778cd8f3/f1.jpg)

图1. 云计算方法与机场乘车的比较。有服务器的是租车，无服务器的是坐出租车。

在无服务器计算中，程序员使用云提供商提供的高级抽象来创建应用程序。例如，他们可以用自己选择的语言（通常是JavaScript或Python），用函数式的 "无状态 "编程来定义云功能a，然后指定这些功能应该如何运行，是响应网络请求还是触发事件。他们还可以使用无服务器对象存储、消息队列、键值存储数据库、移动客户端数据同步等，这一组服务产品被统称为后端即服务（BaaS）。管理型云功能服务也被称为功能即服务（FaaS），今天的无服务器云计算统称为FaaS + BaaS（见图2）。

![](https://dl.acm.org/cms/attachment/fa909c8b-8631-4a14-9541-3420d63ae3cb/f2.jpg)

图2. 无服务器与有服务器的云计算：无服务器在应用程序和底层服务器之间提供了一个抽象的概念。

无服务器的主要创新之处在于隐藏服务器，而服务器本身具有复杂的编程和运营模式。服务器用户必须为可靠性创建冗余，根据负载的变化调整容量，为安全而升级系统，等等。17 这往往需要对分布式系统的故障模式和性能进行困难的推理。工具可以提供帮助，例如，通过启发式地调整容量，这是一种自动缩放的形式，但这些也需要详细的配置和持续的监控。相比之下，无服务器将这些和其他的责任交给了云服务提供商。

无服务器计算的三个基本特征是

提供一个抽象概念，隐藏服务器以及编程和操作的复杂性。
提供一种随用随付的成本模式，而不是基于预订的模式，因此对闲置资源不收费（见图3）。
自动、快速和无限制地增加和减少资源，以密切配合需求，从零到实际上是无限的。

![](https://dl.acm.org/cms/attachment/cfc36b35-a1c9-4d81-9a53-a1d56c0a4c9d/f3.jpg)

图3. 无服务器与有服务器的云计算：无服务器的用户只为所消耗的资源付费，而不是为闲置的保留容量付费。

8,17 回到我们的比喻，出租车服务（无服务器计算）必须提供有执照的司机（隐藏操作），只在提供服务时收费（随用随付），并安排足够的出租车以尽量减少客户的等待时间（自动扩展）。如果出租车不能可靠地提供这三样东西，那么客户可以转而租用和经营汽车（服务器计算）。

最近《通信》杂志的一篇文章很好地介绍了无服务器计算的现状、它与基础设施即服务（IaaS）和平台即服务（PaaS）的区别、它的市场份额、用例以及它的局限性。8 在这篇文章中，我们将分享我们对无服务器计算所代表的演变、影响它的经济力量、它为什么会失败以及它如何演变以发挥其潜力的看法。

我们预测，大部分数据中心的计算将由无服务器计算主导，但我们也相信，无服务器计算将与今天的无服务器产品有很大的区别。特别是，我们相信，新的通用无服务器抽象将出现，增加复杂的状态管理和自动优化，以实现更多的使用案例。无服务器现在依赖于同质的CPU，但在未来，无服务器将简化硬件加速器的使用，如图形处理单元（GPU）或张量处理单元（TPU）19，以支持特定的工作负载--随着摩尔定律的放缓，它们最有可能提供更高的性能。14 虽然今天有人担心无服务器的安全性，但我们认为，精心设计实际上可以使应用开发者更容易保护其软件免受外部攻击。

与2010年一样，我们再次预测，这些挑战将被克服，这个第二阶段将成为云计算的主导形式，通过将云的力量置于所有应用开发者的手中而加速其普及。

## Understanding What Serverless Is Today

云功能8占据了无服务器计算的大部分市场份额，但它们只是无服务器云中众多服务中的一种。围绕FaaS的兴奋是有道理的，因为它让人们看到了通用的无服务器计算的模样，然而BaaS服务包含了更大的、更古老的无服务器服务。

例如，AWS最初提供的S3对象存储是一种远程备份和存档服务，比宣布EC2虚拟机租赁还要早几年。你可以把S3看作是无服务器计算的先驱，它提供 "无磁盘存储"，即提供存储但隐藏磁盘。随着时间的推移，云供应商提供了额外的BaaS服务来帮助有服务器计算。消息队列（例如AWS SQS、谷歌云Pub/Sub）是另一项早期服务。后来出现了键值数据库（例如，谷歌云数据存储、AWS DynamoDB、Azure CosmosDB）和基于SQL的大数据查询引擎（例如，AWS Athena、谷歌BigQuery）。

当AWS Lambda在2015年推出时，它是第一个云功能产品，并提供了独特和引人注目的东西：能够执行几乎所有在服务器上运行的代码。它包括对几种编程语言和任意库的支持，所有这些都是按需付费，在任何规模下安全运行。然而，它对编程模型施加了某些限制，即使在今天也将其限制在某些应用上。这些限制包括最大的执行时间，缺乏持久的状态，以及限制性的网络。

今天，有几个无服务器环境可以运行任意代码，每个环境都迎合了一个特定的使用案例。例如，谷歌云Dataflow和AWS Glue允许程序员将任意代码作为数据处理管道的一个阶段来执行，而谷歌App Engine可以被认为是一个用于构建Web应用的无服务器环境。

这些众多的无服务器产品都具有无服务器计算的三个共同特点：隐藏服务器的抽象性、现收现付的成本模式以及出色的自动扩展性。它们共同提供了一套可供选择的方案，可以结合起来，以满足不断增长的应用范围。

## Serverless Cloud Economics

今天的云计算在很大程度上是由商业考虑和技术进步形成的，其未来也将如此。云客户之所以选择无服务器计算，是因为它允许他们继续专注于解决其领域或业务中的独特问题，而不是服务器管理或分布式系统中的问题。6 这种客户价值主张的力量是对无服务器计算的未来应用感到乐观的主要原因。

虽然无服务器计算由于资源的单价较高而显得更为昂贵（见边栏 "无服务器的成本"），但客户只需为他们正在使用的资源付费，而云提供商则承担了闲置资源的成本。在实践中，客户在将应用移植到无服务器的过程中实现了大量的成本节约。30 虽然这种成本的降低可能会威胁到云提供商的收入，但杰文斯悖论2表明，低价格可以引发消费增长，从而抵消单位成本的降低，导致收入增长。云提供商还通过帮助客户满足可变和不可预测的资源需求来获得盈利机会，他们可以通过共享资源池比客户使用自己的专用资源更有效地做到这一点。16 这种机会也存在于有服务器计算中，但随着资源在更精细的基础上被共享，这种机会也会增加。无服务器计算还为云提供商提供了提高利润率的机会，因为BaaS产品通常代表了传统上由高利润软件产品（如数据库）提供的产品类别。

无服务器的 "即用即付 "模式对云提供商的创新动力有着重要的积极意义。在无服务器之前，自动缩放的云服务会自动提供虚拟机，也就是储备资源，但客户随后要为这种能力付费，即使它一直处于闲置状态。有了无服务器，云提供商为闲置的资源付费，这就为自动缩放创造了 "游戏中的皮肤"，并为确保有效的资源分配提供了激励。同样，由于云提供商直接控制了更多的应用堆栈，包括操作系统和语言运行时间，无服务器模式鼓励在每个层面上进行效率投资。

更有生产力的程序员、更低的客户成本、更多的供应商利润，以及更好的创新，都为无服务器的采用创造了有利条件。16 有服务器的虚拟机抽象是标准化的，主要是基于Linux操作系统和X86指令集，但每个供应商的无服务器云功能和BaaS API都有明显和微妙的不同。由此产生的转换成本使最大和最成熟的云供应商受益，并使他们有动力推广复杂的专有API，以抵制事实上的标准化。简单和标准化的抽象，也许是由较小的云供应商、开源社区或学术界引入的，将消除无服务器应用最突出的剩余经济障碍。

## The Next Phase of Cloud Computing

也许理解无服务器计算所代表的转变的最佳方式是关注第一个基本品质（如前所述）：提供一个隐藏服务器的抽象，从而简化编程和操作模式。从一开始，云计算就提供了一个简化的操作模型，但简化的编程来自于隐藏服务器。无服务器计算的未来发展，以及在我们看来，云计算的发展，将以提供简化云计算编程的抽象的努力为指导。

令人吃惊的是，到目前为止，云计算对程序员工作方式的改变很小，尤其是与它对运营商的影响相比。许多在云中运行的软件与在传统数据中心中运行的软件完全相同。将今天最需要的编程技能与10年前所需的编程技能进行比较，你会发现核心技能组合变化很小，即使特定的技术来了又走。相比之下，操作员的工作已经发生了巨大的变化。安装和维护服务器、存储和网络在很大程度上已经成为过去，取而代之的是对通过云供应商的API管理虚拟化基础设施的关注，以及强调变革管理的技术和组织方面的DevOps运动。

是什么让云的编程变得困难？虽然有可能只用一台服务器来使用云，但这既没有提供容错性，也没有提供可扩展性，更没有提供现收现付，所以大多数云编程很快就变成了分布式系统编程。在编写分布式系统时，程序员必须对数据中心的空间范围、各种部分故障模式以及所有的安全威胁进行推理。用Fred P. Brooks的语言来说，这些问题代表了 "偶然的复杂性"，它产生于实现环境，与 "基本的复杂性 "形成对比，后者是应用程序提供的功能中所固有的。7 在Brooks写作的时候，高级语言正在取代汇编语言，使程序员无需推理复杂的机器细节，如寄存器分配或存储器中的数据布局。正如高级语言隐藏了CPU运行的许多细节一样，无服务器计算也隐藏了建立一个可靠、可扩展和安全的分布式系统所需的许多细节。

接下来，我们将考虑无服务器抽象的其他方法，包括目前存在的方法和我们想象的方法。这些方法争先恐后地回答了 "如果不是服务器，那是什么 "这个问题。我们将这些替代性抽象方法分为特定应用和通用类别（见表1）。特定应用的抽象解决了一个特定的用例，今天的产品中就有几个这样的抽象。通用抽象必须在广泛的用途中运行良好，并且仍然是一个研究挑战。


![](https://dl.acm.org/cms/attachment/b75ab77b-17fa-4047-9f37-e2a26edf4ab9/t1.jpg)

表1. 其他抽象方法。

让我们来看看大数据处理中的一个说明性例子。考虑一个在电子商务环境中可能出现的简单查询：使用从一百万个类别中得出的权重计算100亿条记录的平均值。这个工作负载有可能产生大量的并行性，因此它得益于无服务器的无限资源幻觉。

我们介绍了两个针对特定应用的无服务器产品，以满足这个例子，并说明该类别如何提供多种方法。人们可以使用AWS Athena大数据查询引擎，这是一个使用SQL（结构化查询语言）编程的工具，可以针对对象存储中的数据执行查询。SQL特别适合于分析，可以用一条语句来表达这种计算。另外，人们可以使用一个框架，如谷歌云数据流提供的框架。这样做需要编写一个简单的MapReduce风格的11程序，例如，使用Java或Python，有两个函数：一个是计算某个数据块的加权平均数，另一个是将不同数据块的加权平均数合并为一个数据块的联合。该框架负责处理这些函数的数据输入和输出，以及自动缩放、可靠性和其他分布式系统问题。与基于SQL的工具相比，这种抽象可以运行任意的代码，这可以使它适用于更广泛的分析问题。

为我们的大数据例子提供高性能解决方案的通用无服务器抽象还不存在。云功能似乎提供了一个解决方案，因为它们允许用户编写任意代码，而且对于某些工作负载来说，它们确实如此，28 但由于限制，它们的性能有时比替代方案差得多。13,17 图4说明了如果我们使用云功能实现我们的例子，而不是使用云数据流等特定应用框架，网络流量可能会高很多。通过云功能，供应商将工作分配给不同的虚拟机实例，而不考虑应用程序的通信模式，这简化了自动扩展，但增加了网络流量。

![](https://dl.acm.org/cms/attachment/250c339b-520a-448a-b302-bc127f4c8339/f4.jpg)

图4. 为聚合和广播模式增加通信。

我们建议通过两条途径来增强云计算功能，使其在更广泛的应用中运行良好，有可能将其变成通用的无服务器抽象。首先，我们设想，由程序员提供的提示可以指出如何实现更好的性能。提示可以描述应用程序的通信模式（例如，广播或全还原），或建议任务放置的亲和性。25 这种方法在编译器中已有先例（例如，分支预测、对齐和预取提示）。

第二，而且更有说服力的是，我们设想通过自动优化来消除低效率。在我们的例子中，云提供商可能承诺从观察到的通信模式中推断出位置优化。在某些情况下，这种推断也可能是基于对程序的分析而静态地做出的。在单机背景下，这在现代编译器和语言运行时的工作中有着充分的先例，人们可以认为这种形式的无服务器计算是将语言支持扩展到分布式系统。

图5说明了特定应用和通用的无服务器抽象之间的区别。在通用情况下，云提供商公开了一些基本的构建模块，例如，增强版的云功能和某种无服务器存储。各种特定的应用案例可以建立在这些基础之上。通过特定应用的无服务器，云提供商提供了大量的BaaS，以满足越来越多的应用的需求。

![](https://dl.acm.org/cms/attachment/2ad35101-825b-46e9-bfa5-9ce6665f7451/f5.jpg)

图5. 无服务器的潜在未来方向。

今天，无服务器计算仍然完全是针对特定应用的。即使是可以执行任意代码的云函数，也主要在无状态API服务和事件驱动的数据处理方面很受欢迎。27 我们预计特定应用的无服务器计算将会增长，但我们对潜在的通用无服务器抽象的出现最感兴奋，它可以承载满足各种需求的软件生态系统。在我们看来，只有通用的方法才能最终取代服务器，成为云计算编程的默认形式。然而，通用的无服务器技术今天并不存在，开发它也带来了研究方面的挑战。

## Research Challenges

无服务器计算正在迅速发展，并提供了各种研究挑战，其中许多挑战是特定应用和通用无服务器的共同挑战。

状态管理。分布式云计算应用往往需要在其组件任务之间交换短期或短暂的状态。这方面的例子包括应用范围内的缓存、索引和其他查询表，或大数据分析的中间结果。今天的云功能允许应用程序在每个功能中本地存储短暂的状态，这对缓存和作为程序的工作内存很有用。无服务器的共享状态可以保存在对象存储或键值存储中，但这些都不能像服务器那样同时提供低延迟、低成本、高吞吐量和细粒度的访问。17 解决这些挑战的方法包括用于分析的临时数据存储21 以及整合缓存和提供一致性保证的有状态的云功能。

网络。云功能将安排工作的责任从用户转移到云提供商，这有几个有趣的后果。由于用户放弃了对功能运行时间的控制，在云功能之间传递状态需要通过共享存储；直接的网络通信是没有意义的，云提供商会阻止它。访问共享存储会增加大量的延迟，有时甚至是几百毫秒的延迟。用户也放弃了对功能运行位置的控制，从而排除了服务器常见的优化，包括在任务之间共享共同的输入，以及在通过网络发送输出之前合并输出（见图4和之前的讨论）。克服这些挑战的尝试将凸显出给予程序员更多控制权和允许云提供商自动进行优化之间的矛盾。

可预测的性能。FaaS和BaaS都可以表现出可变的性能，这就排除了它们在必须满足严格保证的应用中的使用。部分原因是根本性的：无服务器提供商依靠统计复用来创造无限资源的假象，同时拒绝用户对资源超额订阅的控制。总有一些机会，不幸的时机会造成排队延迟。将资源从一个客户重新分配给另一个客户也有延迟成本，在云功能背景下，这被称为 "冷启动"。冷启动延迟有几个部分，17 其中重要的是初始化功能的软件环境所需的时间。在这个领域已经有了进展。云功能环境，如谷歌gVisor和AWS Firecracker1现在可以在大约100毫秒内启动，而传统的虚拟机需要几十秒才能启动。24 AWS Lambda的客户还可以通过购买 "供应并发 "来避免冷启动延迟，这在无服务器模式中重新引入了一种资源预订的形式，颇具争议。我们还希望看到基于统计保证或服务水平目标（SLOs）的定价，这在今天的无服务器中是不存在的。

安全性。无服务器计算导致了细粒度的资源共享，因此增加了侧信道攻击的风险，即攻击者利用实际硬件的微妙行为，这些行为与规范或程序员的假设不同（见侧边栏 "无服务器与安全"）。威胁包括对DRAM的Rowhammer攻击20和利用微架构漏洞的攻击22。除了采用为无服务器计算开发的缓解措施外，无服务器可能采用随机调度，使攻击者更难瞄准特定的受害者。无服务器计算还可能通过网络通信产生更大的信息泄漏，因为应用程序的细粒度分解和其碎片的物理分布。观察网络流量大小和时间的攻击者，即使它是加密的，也可能对私人数据做出推断。解决这些风险可能要通过遗忘计算来实现。

编程语言。简化的分布式系统编程是无服务器计算的一个核心优势，18 虽然以前在这个领域的很多工作都是相关的，但无服务器的环境需要一个新的视角，并增加了紧迫性。传统的挑战包括容错性、一致性、并发性，以及来自定位的性能和效率。新的挑战包括对自动扩展、随用随付和细粒度复用的一流支持。

由于试图将无服务器计算扩展到无状态的云函数之外，容错问题也随之升华。Azure持久功能使用C#语言特性来提供透明的检查点，这使得编写有状态和可恢复的无服务器任务更加容易。微软奥尔良5实现了一个行为体模型15，它同样向程序员隐藏了容错问题。行为体还提供了一个定位的概念，可以作为有状态的无服务器计算的云函数的对应物。Ray25体现了两者的元素。实现一致性的方法包括由Argus开创的语言集成交易。23 然而，交易充满了性能和可扩展性的挑战，而自动扩展的无服务器环境可能会加剧这种挑战。另一种方法是像Bloom3这样的语言，它可以通过自动分析来确定程序的哪些部分可以独立运行，无需协调，从而实现可扩展。现收现付应该鼓励语言开发者重新思考资源管理问题，例如，自动垃圾收集可能会适应计量内存的定价。云计算编程的语言方法，9 直面分布式系统编程的复杂性，可能代表了简化云计算编程的最直接和雄心勃勃的方法。

机器学习。我们相信，机器学习的自动优化将在以上讨论的所有领域发挥重要作用。它可以帮助决定在哪里运行代码，在哪里保持状态，何时启动一个新的执行环境，以及如何在满足性能目标的同时保持高利用率和低成本。它还可以帮助识别威胁安全的恶意活动，或自动将大型程序切割成可以在独立的云功能中执行的片段。机器学习也可以帮助优化有服务器的计算，10 但无服务器的抽象给了云提供商对相关旋钮的更多控制权，以及训练强大有效的模型所需的对众多客户的可见性。

硬件。目前的硬件趋势可能是对无服务器计算的补充。主导云计算的x86微处理器在性能上几乎没有提高；2017年，程序延迟只提高了3%，14这一趋势如果继续下去，意味着性能在20年内不会翻倍。同样，摩尔定律的结束正在减缓每片DRAM容量的增长。业界的反应是引入了特定领域架构（DSA），这些架构是为特定类型的问题量身定做的，提供了显著的性能和效率提升，但在其他应用中表现不佳。GPU和TPU在狭窄的任务中可以比CPU的性能高出30倍。19 这些例子是众多例子中的第一个，因为用DSA增强的通用处理器将可能成为常态。

令人吃惊的是，到目前为止，云计算对程序员工作方式的改变很小，尤其是与它对运营商的影响相比，更是如此。

我们相信无服务器计算可以为整合不同的架构提供一个有用的编程模型，例如在不同的加速器上运行独立的云功能。它还有助于通过提高抽象水平为创新创造空间，例如，允许云提供商在识别到可能受益的工作负载时用DSA代替CPU。

## Why Serverless Computing Might Still Fail

虽然我们相信无服务器计算可以发展成为云计算编程的默认模式，但我们也可以想象到无服务器计算保持其主导地位的几种情况。首先，有服务器的计算是一个移动的目标，它在不断地改进，尽管速度很慢。曾经按小时计费的云计算虚拟机现在的最小计费增量是一分钟，此后按秒收费。容器和虚拟机协调工具（例如，Kubernetes、Terraform）有助于简化复杂的部署，并且越来越多地将管理任务自动化，如进行备份。程序员在构建应用程序时可以依靠成熟的软件生态系统和强大的传统兼容性，而公司已经拥有熟练的服务器云部署的团队。服务器硬件也在不断变大变强，将CPU、内存和加速器的能力集中在一个紧密耦合的环境中，这对某些应用来说是一个好处。

其次，今天成功的无服务器产品属于特定的应用类别，目标狭窄，而通用的无服务器抽象则更有可能取代有服务器计算（也是通用的）。然而，通用的无服务器计算面临着一些障碍：我们所设想的技术还不存在，而且对于云计算供应商来说，它可能是一个不太有利可图的业务。

最后，即使我们的设想得以实现，"无服务器计算 "这个品牌也可能无法生存。将旧产品贴上下一个新事物的标签的诱惑力很强，会在市场上造成混乱。我们很高兴看到谷歌应用引擎（Google App Engine）等产品获得了无服务器的称号，以及随之而来的扩展到零等功能。但是，如果这个词被半心半意的努力所冲淡，那么也许通用的无服务器计算会以另一个名字出现。

## Conclusion and Predictions

云计算正在蓬勃发展并不断演变。正如我们预测的那样，它已经克服了2010年面临的挑战。4由于提供了更低的成本和简化的系统管理，该业务每年增长高达50%，并证明了云计算供应商的高利润。云计算现在正进入第二个阶段，它的持续增长将由一个新的价值主张推动：简化的云编程。

就像叫出租车比租车简化了交通一样（见图1），无服务器计算使程序员不再考虑服务器和与之相关的一切复杂问题。按照同样的命名惯例，你可以把出租车服务归类为无车运输，因为乘客不需要知道如何操作汽车就可以乘车。无服务器提高了云计算的抽象水平，采用随用随付的定价方式，并迅速将资源自动扩展到零，直至达到实际上的无限量。

无服务器计算仍在发展中，在定义其抽象概念和实现这些抽象概念方面，仍有许多开放性问题。我们（大胆地）以对无服务器计算在未来十年的五个预测来结束本文。

今天的FaaS和BaaS类别将让位于更广泛的抽象，我们将其归类为通用无服务器计算或特定应用无服务器计算。虽然有服务器的云计算不会消失，但随着无服务器计算克服其目前的局限性，其在云中的相对使用将下降。
我们期望新的通用无服务器抽象能够支持几乎所有的用例。它们将支持状态管理，以及优化--无论是用户建议的还是自动推断的--以实现与有服务器计算相当甚至更好的效率。
我们认为无服务器计算的成本没有理由超过有服务器计算的成本。我们预测，随着无服务器计算的发展和普及，几乎所有的应用，无论是小规模还是大规模的应用，在无服务器计算中的成本都不会增加，而且可能会降低很多。
机器学习将在无服务器实现中发挥关键作用，使云供应商能够优化大规模分布式系统的执行，同时提供一个简单的编程接口。
用于无服务器计算的计算机硬件将比今天为其提供动力的传统X86服务器更加异质化。
如果这些预测成立，无服务器计算将成为云时代的默认计算范式，在很大程度上取代有服务器的计算，从而结束客户端-服务器时代，就像智能手机带来的PC时代的结束一样。

鸣谢。我们感谢审稿人的深思熟虑的意见，以及许多对早期草案提供反馈的朋友。这项工作是在加州大学伯克利分校RISELab进行的，它得到了国家科学基金会考察项目、阿里巴巴集团、亚马逊网络服务、蚂蚁金服、爱立信、Facebook、Future-wei、谷歌、英特尔、微软、苏格兰银行、Splunk和VMware的支持。

References
1. Agache, A., et al. Firecracker: Lightweight virtualization for serverless applications. In Proceedings of the 17th USENIX Sym. Networked Systems Design and Implementation (2020), 419–434.

2. Alcott, B. Jevons' paradox. Ecological Economics 54, 1 (2005), 9–21.

3. Alvaro, P., et al. Consistency analysis in Bloom: A CALM and collected approach. CIDR, 249–260.

4. Armbrust, M., et al. A view of cloud computing. Commun. ACM 53, 4 (Apr. 2010) 50–58.

5. Bernstein, P., et al. Orleans: Distributed virtual actors for programmability and scalability. MSR-TR-2014-41, 2014.

6. Brazeal, F. The business case for serverless, 2018; https://www.trek10.com/blog/business-case-for-serverless

7. Brooks, F. No silver bullet: essence and accidents of software engineering. In Information Processing. IEEE, 1986.

8. Castro, P., et al. The rise of serverless computing. Commun. ACM 66, 12 (Dec. 2019), 44–54.

9. Cheung, A., Crooks, N., Milano, M., and Hellerstein, J. New directions in cloud programming. CIDR, 2021.

10. Dean, J. Machine learning for systems and systems for machine learning. In Proceedings of the 2017 Conf. Neural Info. Processing System.

11. Dean, J. and Ghemawat, S. MapReduce: simplified data processing on large clusters. Commun. ACM 51, 1 (Jan. 2008), 107–113.

12. Goldreich, O. Towards a theory of software protection and simulation by oblivious RAMs. In Proceedings of the 19th Annual ACM Symposium on Theory of Computing, (1987) 182–194.

13. Hellerstein, J., et al. Serverless computing: One step forward, two steps back. CIDR, 2019.

14. Hennessy, J. and Patterson, D. A new golden age for computer architecture. Commun. ACM 62, 2 (Feb. 2019), 48–60.

15. Hewitt, C., Bishop, P., and Steiger, R. A universal modular actor formalism for artificial intelligence. In Proceedings of the 3rd Intern. JoinConf. Artificial Intelligence. (1973), 235–245. Morgan Kaufmann Publishers Inc.

16. Irwin, D. and Urgaonkar, B. Research Challenges at the Intersection of Cloud Computing and Economics. National Science Foundation, 2018.

17. Jonas, E. et al. Cloud programming simplified: A Berkeley view on serverless computing. Tech. Rep. No. UCB/EECS-2019-3, 2019.

18. Jonas, E., Pu, Q., Venkataraman, S., Stoica, I., and Recht, B. Occupy the cloud: Distributed computing for the 99%. In Proceedings of the ACM SoCC, 2017.

19. Jouppi, N. et al. In-datacenter performance analysis of a tensor processing unit. In Proceedings of the 44th Annual Intern. Symp. Computer Architecture. (2017), 1–12.

20. Kim, Y., et al. Flipping bits in memory without accessing them: An experimental study of DRAM disturbance errors. In Proceeding of the 42nd ISCA. IEEE Press, 2014, 361–372.

21. Klimovic, A., et al. Pocket: Elastic ephemeral storage for serverless analytics. In Proceedings of the 13th USENIX Symp. Operating Systems Design and Implementation (2018), 427–444.

22. Kocher, P., et al. Spectre attacks: Exploiting speculative execution. Commun. ACM 63, 7 (July 2020), 93–101.

23. Liskov, B. Distributed programming in Argus. Commun. ACM 31, 3 (Mar. 1988), 300–312.

24. McIlroy, R., Sevcik, J., Tebbi, T., Titzer, B., and Verwaest, T. Spectre is here to stay: An analysis of side-channels and speculative execution. 2019; arXiv:1902.05178.

25. Moritz, P., et al. Ray: A distributed framework for emerging AI applications. In Proceedings of the 13th USENIX Symp. Operating Systems Design and Implementation (2018), 561–577.

26. Oakes, E., et al. SOCK: Rapid task provisioning with serverless-optimized containers. In 2018 USENIX Annual Technical Conf. (2018), 57–70.

27. Passwater, A. 2018 serverless community survey: Huge growth in serverless usage; https://serverless.com/blog/2018-serverless-community-survey-huge-growth-usage/

28. Perron, M., Fernandez, R., DeWitt, D., and Madden, S. Starling: A scalable query engine on cloud functions. In Proceedings of the 2020 ACM SIGMOD Intern. Conf. Management of Data (2020), 131–141.

29. Sreekanti, V., et al. Cloudburst: Stateful functions-as-a-service. Proc. VLDB 13, 11 (2020), 2438–2452.

30. Wagner, T. Debunking serverless myths, 2018; https://www.slideshare.net/TimWagner/serverlessconf-2018-keynote-debunking-serverless-myths
