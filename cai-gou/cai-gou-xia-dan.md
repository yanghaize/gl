# **采购系统使用说明文档**

采购系统简单来说主要分为这几大部分：采购下单、财务审核、付款、质检审核及入库等；

详细流程如下所示：

![](/assets/113import.png)

注意：准采购单提交财务（经理）审核通过后，采购单状态就是质检审核中了，质检审核中的采购单，质检审核、申请付款可以并行进行，没有先后顺序；当采购单的SKU产品完成入库并付清款项之后，这个采购单才算完结；

**采购系统使用说明文档**

采购系统简单来说主要分为这几大部分：采购下单、财务审核、付款、质检审核及入库等；

详细流程如下所示：

注意：准采购单提交财务（经理）审核通过后，采购单状态就是质检审核中了，质检审核中的采购单，质检审核、申请付款可以并行进行，没有先后顺序；当采购单的SKU产品完成入库并付清款项之后，这个采购单才算完结；

现从采购下单，审核，付款，质检，入库这几个方面对采购流程作详细的说明：

**【采购下采购单】**

采购下采购单有三种方式：1、新品计划直接生成新品采购单；2、智能预警生成采购单；3、SKU特批审核生成采购单；

**A、新品计划生成采购单**

新品计划列表中的SKU都是新品开发同事新开发的SKU产品，先前没有下过采购单，且当前SKU产品状态不是清货完毕的，这些新SKU产品都会进入到新品计划中。

![](/assets/114import.png)

注：新品计划中的SKU是由当前SKU所属人负责下单；

查看SKU供应商是否被绑定给其它采购助理，可以到V3系统【采购管理】-&gt;【绑定供应商查询】页面中查询即可；

新品计划生成新品采购单：

由于目前我们采购系统是按供应商下单，因此对新品SKU下采购单时，在新品计划列表中选择一个供应商，点击供应商链接进入的就是此供应商的SKU新品下单页面，在此页面中勾选要下单的供应商SKU，然后再到页面最下方选择下单仓库，然后点“生成新品采购单”按钮，即可生成新品采购单，生成的新品采购单就会直接到准采购单列表中（新品采购单号是以NPO-开头的，其它方式生成的采购单都是以PO-开头的）；如下图所示：

![](/assets/115import.png)

![](/assets/116import.png)

（生成新品采购单）

注：新品SKU的采购规则：采购价为0-5元的最多只能采50个，大于5元的最多只能采12个，如果需要采购更多数量则走特批通道；当新品SKU在新品计划中生成新品准采购单后，这个SKU就不会再显示在新品计划中；

![](/assets/117import.png)

新品计划生成的准采购单都会到准采购单列表的新品采购单列表中；

**B、智能预警生成采购单**

每天达到预警条件的SKU都会到智能预警列表页面中，智能预警的统计是每天2次（每天8：50和12：50各统计一次）；V3里面的预警数据可能和当前新ERP系统的预警数据有点不同，因为V3里面的是实时数据，我们这里的预警数据不是实时数据，但是不管怎样，只要是达到了预警条件的话，下一次统计预警数据的话就会自动预警进来的；

![](/assets/118import.png)

同样，智能预警里面的SKU的供应商如果被绑定给其它采购助理下单，则此SKU由被绑定的采购助理来下单（本人会看不到此SKU），如果SKU的供应商未绑定给采购助理，则由之前的采购助理来下单；现时也可以通知杨巧对供应商进行绑定；

**1）、生成采购计划**

在智能预警页面，点‘一键转入采购计划’按钮，则智能预警中的SKU就会批量转入采购计划中；

![](/assets/119import.png)

生成的采购计划如上图所示（注：这里用的是测试系统的数据，可能会数据不全，所以会有空的，线上正式环境下不会出现空的数据）

由于我们采购系统按供应商进行下单，所以采购计划中，是以供应商列表来显示的，点击供应商名称进入采购计划详细页面就可以看到当前供应商的SKU采购计划列表；

![](/assets/120import.png)

（采购计划详情页面）

注意：当前页面中SKU的预定数量不能超过预警数量的10%，可修改当前默认的采购价；

**2）、生成预采购单**

在采购计划SKU详情页面中，勾选需要下单的SKU，再点击页面最下面的“生成预采购单”按钮即可生成预采购单；

![](/assets/121import.png)

![](/assets/122import.png)

**预采购单的4个状态：未完成、已完成、已结算、特批审核中；**

【未完成】状态是指还未全部生成准采购单的预采购单；这里面包括通过采购计划新生成的预采购单以及生成了部分采购单的预采购单；

![](/assets/126import.png)

【已完成】状态是指已全部生成准采购单的预采购单；

![](/assets/127import.png)

【已结算】状态是指已下了部分准采购单的预采购单，还有部分没有下准采购单的，并且不想再继续下余下部分采购单就已经完结的预采购单；

![](/assets/128import.png)

【特批审核中】状态是指需要特批审核的预采购单；特批审核中的预采购单是通过添加特批SKU生成的特批预采购单，这种预采购单都会到“特批审核中”的状态中等待财务审核（或者杨巧和王锋审核）；一旦财务审核通过，则特批审核中的预采购单就会到“未完成”预采购单列表中；

![](/assets/129import.png)

**3）、生成准采购单**

在预采购单”未完成”列表页面中，点击预购单号就会进入预采购单详情页面，如下图所示

![](/assets/130import.png)

![](/assets/131import.png)

在预采购单详情页面中，勾选需要生成准采购单的SKU，并填写确认采购数量，然后选择仓库，再点“生成准采购单”按钮即可生成准采购单；

![](/assets/133import.png)

（生成准采购单）

**C、特批通道生成采购单**

除了通过新品生成新品采购单，通过智能预警生成预警采购单，还有一种情况就是通过特批通道生成采购单；

**1）、添加特批SKU**

在“特批/按SKU采购计划”页面中，点击“添加特批采购SKU”按钮即可弹出添加特批SKU的窗口，如下图所示：

![](/assets/134import.png)

![](/assets/135import.png)

在添加特批SKU窗口中，选择仓库，填写特批SKU，然后点“提交”即可生成特批SKU，如下图所示：

![](/assets/136import.png)

**2）、特批SKU提交经理审核生成特批预采购单**

添加特批SKU后，勾选要特批的SKU，填写特批理由，然后将SKU提交经理审核，走特批流程，如下图所示：

![](/assets/137import.png)

特批SKU提交经理审核后就会生成特批预采购单，在预采购单列表的“特批审核中”即可看到生成的待特批预采购单，如下图所示：

![](/assets/138import.png)

注意：此时生成的预采购单是特批审核中，等待特批审核；

**3）、特批预采购单生成准采购单**

特批审核通过后，特批预采购单就会到预采购单列表的“未完成”状态列表中；这时，像先前一样按照预采购单生成准采购单的流程来生成准采购单即可，这里就不再赘述；

**【准采购单管理及审核】**

上面采购单生成之后，就会都到“准采购单”列表页面，现对采购单作详细说明：

准采购单共分为13种状态：新品采购单、未处理准采购单、经理审核中、财务已完成、质检审核中、财务驳回单、异常入库单、正常已完成、异常完成、待特批、已申请取消、财务确认可取消、已申请异常结单；如下图所示：

![](/assets/140import.png)

现对每种状态作详细说明；

**新品采购单：**通过新品计划生成的采购单；

**未处理准采购单：**通过智能预警或特批SKU生成的还未处理的准采购单；

**经理审核中：**未处理准采购单提交经理审核后，采购单状态就会变成经理审核中，采购单就会到经理审核中列表中等待财务审核；

**质检审核中：**经理审核中的准采购单财务审核通过后，采购单状态就会变成质检审核状态，此状态下的采购单仓库那边可以采购单SKU进行质检审核及入库，同时采购也可以对采购单申请付款了；

**财务驳回单：**财务驳回单是采购将准采购单提交经理审核不通过后就会到财务驳回单里面，还有其它情况下的财务驳回的采购单也会到财务驳回单中；财务驳回单需要采购修改采购单信息后再次提交经理审核，财务审核通过后，采购单才会到质检审核中状态；

**异常入库单：**异常入库单是有入库单有异常的采购单；

**正常已完成：**正常已完成的是采购单所有SKU质检审核通过且已全部入库完成的采购单；

**异常完成：**异常完成的是因采购单有部分或全部SKU没有来货而结单的采购单就是异常完成的采购单；

**待特批：**待特批采购单是采购单申请付款时，因采购单SKU价格高于当前最新采购价而转入等待特批的采购单；

**已申请取消：**已申请取消的采购单是在待申请付款中因不想付款而需要删除的采购单申请取消，财务还没有处理取消申请的状态（注：申请取消采购单功能在待申请付款页面中）；

**财务确认可取消：**财务确认可取消的采购单是采购在待申请付款中因不想付款而需要删除的采购，申请取消采购单后，财务确认采购的取消申请通过后的状态，这种状态下采购单就可以操作回退删除采购单了；另外，对于财务确认可取消的采购单，如果不想取消，想重新申请付款，则可以在准采购单列表页面中搜索这个采购单，然后操作撤销取消采购单功能即可将采购单放入待申请付款列表中进行申请付款；

**已申请异常结单：**已申请异常结单的采购单是采购对采购单申请了异常结单，但是财务还没有处理采购的异常结单申请是的状态，当财务处理了异常结单申请后，采购单的状态就变成异常完成状态了；

**撤销取消采购单：**撤销取消采购单是指当前采购单状态为已申请取消或财务确认可取消，这两种状态下采购单是不可以申请付款的，撤销取消采购单后，采购单的取消状态就会被撤销掉了，这时，采购单就可以申请付款或申请异常结单了（注：撤销取消采购单功能在状态为已申请取消和财务确认可取消这两个状态的列表中）；

【**注意：】**申请付款或申请异常结单的付款申请单，财务驳回后采购单的状态不会变更（采购单状态不会变成财务驳回单，而是保持原始状态）；采购申请驳回付款申请单，然后财务确认驳回后，则这个采购单的状态也不会变更；财务操作已完结驳回付款申请单，采购单的状态会变成财务驳回单；

在准采购单列表页面中，未付款的采购单可以操作修改采购单价格，付款方式，供应商订单号，交易号，运费，折扣等，一旦采购单已付款，有付款记录了，就不可再进行修改采购单信息了，这个时候如果想要修改采购单信息就需要让财务驳回这个采购单，然后再在财务驳回单列表中找到这个采购单修改即可，需要注意的一点是，付款的采购单驳回之后只能在付款申请单中修改运费和采购价，准采购单中不能修改；

![](/assets/142import.png)

![](/assets/143import.png)

![](/assets/144import.png)

![](/assets/145import.png)

（如图所示，可以修改采购价，及付款方式，供应商订单号，交易号，运费，折扣等信息）

（点“提交经理审核”按钮后，采购单状态就成经理审核中）

采购单到经理审核中状态，就表明采购单已经提交经理审核了，审核还没有被处理；

注意：对于新生成的准采购单来说状态为未处理准采购单、新品采购单的采购单需要提交经理审核，然后审核通过后，才能申请付款和质检审核以及仓库操作入库，不然不能操作入库；另外还有一种情况仓库那边可以操作入库，就是当采购单状态为财务驳回单时，这个时候可以重新提交经理审核，审核通过后，采购单状态就会变为质检审核中，这个时候也可操作入库，因此对于已付款完毕或采购单状态已变成正常已完成或异常完成状态下想重新入库产品，那就需要用到这个功能，就是找财务驳回这个采购单，然后重新提交审核就可以了；

**【采购单质检审核及入库】**

采购单质检审核及入库，是仓库那边操作的，这里只作简单说明；对于新生成的采购单（未处理准采购单和新品采购单）只有在准采购单列表页面点采购单号进入采购单SKU明细页面提交经理审核，然后财务那边审核通过之后，采购单就会到质检审核状态列表中，如下图所示：

![](/assets/146import.png)

状态为质检审核中的采购单才仓库那边才可以操作质检以及产品入库，这时也可以申请付款了，申请付款和质检入库是没有先后顺序的，是可以同时并行进行的；质检入库完毕，采购单SKU全部入库齐全这时采购单就流入正常已完成了；

**注意：**采购单状态为正常已完成或异常完成，则这个采购单不一定就完结了，这个时候需要看采购单是否已经付款完毕，如果采购单已全部付款完成，这个时候才算这个采购单完结了，不然这个采购单是未完结的，还有一种情况就是如果一个采购单的付款申请单状态是“需退款”状态，那这个采购单也未完结，也需要退款完毕才算完结，这个在后面的采购单付款环节会有说明。

**【采购单未付款异常结单】**

之所以把采购单未付款异常结单单独拿出来说，主要是因为这个异常结单不涉及到付款；

![](/assets/147import.png)

未付款异常结单顾名思义就是未付款的采购单申请异常结单的列表，这里的采购单是不想付款就申请异常结单。所有未申请付款的状态为质检审核中、异常入库单的采购单都会自动到未申请付款异常结单列表中，在未付款异常结单列表中的采购单并不一定需要申请异常结单，这个是根据采购各人需要操作申请异常结单，不需要异常结单就不要去操作申请异常结单，当采购单的在向后流的过程中，随着采购单状态的变更，采购单将不再显示在未付款异常结单列表中。

对未付款的采购单操作申请异常结单，如下图所示：

![](/assets/148import.png)

在未付款异常结单列表采购右侧点击当前采购单的申请异常结单图标，然后会弹出如上图所示的编辑申请异常结单信息的窗口。如果只是采购单的部分SKU申请异常结单，则需要勾选这个采购单的异常结单的SKU，并填写异常数量（SKU异常数量默认是系统按照 采购数量 – 质检数量 自动计算的，如果觉得这个数量有误，可以在输入框中手动修改）和异常结单的备注说明；如果需要将采购单的所有SKU都异常结单，则不需要勾选下面的采购单SKU，只需要在上面的“结束采购单”列表中勾选需要SKU全部异常结单的采购单，然后填写这个采购单的异常结单备注说明，然后点击“异常结单”按钮即可。

对未付款采购单申请异常结单后，当前采购单的状态就变成了“已申请异常结单”， 这时候等待财务处理你的这个异常结单申请即可，当财务处理了你的申请后，这个采购单状态就会就成异常完成了，这样采购单就会到异常完成采购单列表中了。

**【采购单付款】**

**采购单付款流程简单来说就是：申请付款，申请退款，申请异常结单，申请驳回这几个部分；**

**财务则是主要是：确认付款，确认退款，确认异常结单，操作驳回；**

下面先对这些作简单的解释说明，后面会有详细的操作说明，请大家从前到后详细了解，不要跳跃浏览，在看后面的详细操作说明时可以结合这里的简单说明增加理解，就可以明白不同的情况有不同的操作；

**申请付款：**

申请付款分两种情况：

1. **对从未付款的新采购单申请付款；**

一般的生成的采购单提交经理审核后，这个采购单就会到财务待审核里面，财务审核这个采购单通过之后，这个单就会到我们的待申请付款列表页面里，这时，这个采购单就可以申请付款了。

1. **对已部分付款的申请余下部分的付款；**

对于已部分付款的，还有余下部分未付款，我们这时候可以发起第二次付款申请；

**申请退款：**

申请退款也分两种情况：

1. **仅申请退款，但是不结单**

这种情况是当需要仅仅单纯退一笔款的，可以仅申请退款，这种情况申请了退款，但是退款了的话这单并不会完结，可以再次申请退款或申请付款或申请异常结单都可以；

1. **申请退款且异常结单**

这种情况是付款的同时异常结单，如果申请被财务确认的话则这个单退款的同时也异常结单了，就是一步完成退款和异常结单；

**申请异常结单：**

申请异常结单也分两种情况：

1. **单纯对未申请付款的采购单申请异常结单**

这种情况是对那种还未申请付款也未付过款的采购单直接申请异常结单，这种情况不会走付款的步骤就直接把采购单异常完结；

1. **对已申请过付款的申请异常结单**

已申请过付款的申请异常结单，是对有申请过付款，且付款未完成的采购单申请异常结单；这种情况是已经生成过付款申请单，申请异常结单实际上是对付款申请单所属的采购单操作的；

现在对采购付款作详细操作说明：

采购的无纸化付款功能分4个大页面：待申请付款，可申请异常结单，付款申请单，采购单明细；

**1、待申请付款**

待申请付款页面显示的列表是所有已通过财务审核的可申请付款的新采购单，如下图所示；

![](/assets/150import.png)

进入该页面中默认显示的时所有待申请付款的新采购单；另外，还可以根据上面的条件选择功能搜索符合条件的需要申请付款的采购单；

**申请付款共有三个功能：单个采购单申请付款，多个采购单批量申请付款，多个采购单批量合并申请付款；**

【**单个采购单申请付款】：**

如下图所示，点击这个采购单最右边的申请付款图标，弹出申请付款页面，操作申请付款；

![](/assets/151import.png)

（选择申请付款）

注意：不同的付款方式的采购单申请付款页面有点不同，请看下图：

![](/assets/153import.png)

（支付方式为银行转账的申请付款页面）

注意：银行转账支付方式，填写账号信息时，开户行需要写清楚哪个银行哪个分行或支行，还有银行账号也要正确填写，方便财务快付款；

![](/assets/154import.png)

（支付方式为支付宝支付的申请付款页面）

通过上面的截图，我们可以看到申请付款时，付款类型分为两种：全额付款和部分付款；

系统默认显示为全额付款，申请付款金额为应付总金额（**应付总金额=SKU总金额+运费-折扣金额**）；如果需要申请部分付款就选择部分付款即可，然后点【申请付款】按钮提交申请付款；提交申请付款成功后会自动生成一个付款申请单，在【付款申请单】页面的待付款列表里面可以找到当前采购单生成的付款申请单；

**【多采购单批量合并申请付款】**

多采购单批量合并申请付款：是指同一供商同一制单人同一支付方式的多个采购单可以批量合并提交申请付款，这时，它只会生成一个付款申请单，这个付款申请里面包含了多个采购单，付款申请单的总金额就是这多个采购单的应付总金额；

注意：批量合并申请付款时，支付方式为支付宝的采购单在提交批量合并申请付款它不会合并生成一个付款申请单，而是每个采购单单独生成一个付款申请单；

批量合并申请付款时，可以根据顶部的条件选择功能通过支付方式或供应商可查询同一供应商同一支付方式的采购单来批量提交申请付款；

![](/assets/155import.png)

（批量合并申请付款）

![](/assets/157import.png)

（支付方式为银行付款或现金支付的批量合并申请付款编辑页面）

![](/assets/158import.png)

（支付方式为支付宝的批量合并申请付款编辑页面）

多个采购单的批量合并申请付款，可以对这些采购单设置为全额付款或者部分付款；批量合并申请付款生成的付款申请单也是在【付款申请单】页面的待付款列表里面可以找到当前采购单生成的付款申请单信息；

【**多个采购单批量申请付款】（不合并提交申请）**

多个采购单批量不合并申请付款，是对不同采购单不区分条件的情况下批量提交申请付款，不要求同一供应商同一付款方式；这种方式是每个采购单都独立生成一个付款申请单，也就是说付款申请单里面只有一个采购单；

![](/assets/159import.png)

（批量不合并申请付款）

![](/assets/161import.png)

（批量不合并申请付款编辑页面）

可以看到批量不合并申请付款，在编辑页面是每个采购单一行；

![](/assets/163import.png)

（合并申请付款的可以在付款申请单页面待付款页面找到）

**2、未付款异常结单**

未付款异常结单页面的采购单列表是所有采购单状态为异常入库单或质检审核中的都可以申请异常结单；这里都是针对采购单申请异常结单，还有一种情况是针对付款申请单申请异常结单的，在后面会讲到的。这里的申请异常结单一般都是针对没有付款申请或没有付过款的采购单直接操作申请异常结单；如果是要对已生成过付款申请单的采购单操作申请异常结单最好去【付款申请单】页面找到需要异常结单的付款申请单来操作申请异常结单即可；

注意：在当前可申请异常结单页面选择的采购单申请异常结单，如果该采购单已生成过付款申请单，那么申请异常结单的话它的付款申请单也会被标记为申请异常结单。

![](/assets/164import.png)

（可申请异常结单列表页面）

![](/assets/165import.png)

（申请异常结单编辑页面）

在申请采购单异常结单时，如果只想申请部分SKU异常结单，则只需要勾选这个SKU，并填写异常数量（默认的异常数量是系统自动按照采购数量和已质检数量的差值计算的，可自行修改）和异常结单备注即可；另外，如果需要整个采购单都异常结单，则只需要勾选最上面的“结束采购单”中的采购单并填写异常结单备注即可，下面的SKU可以不需要勾选填写。

**3、付款申请单**

付款申请单列表页面是管理所有已生成的付款申请单信息的，有关付款申请单的任何操作都可以在这个里面进行；

![](/assets/167import.png)

（付款申请单管理页面）

付款申请管理页面共有13个状态：待付款、待申请付款、已驳回、可申请退款、全额付款、部分付款、需退款、异常完成、全额退款、已申请退款、已申请异常结单、已完结撤销付款、已完结驳回；

**待付款：**是已提交申请付款，但是财务还没有操作确认付款的付款申请单；

**待申请付款：**是付款申请单已经部分付款，还有部分金额未付的等待申请付款的付款申请单；这里一般是采购单在申请付款的时候申请的部分付款，因此财务确认付款后，还有部分金额未付款的，可以在这个里面再次申请余下部分的付款；

**已驳回：**分四种情况：付款申请被驳回，退款申请被驳回，异常结单申请被驳回，已完结驳回；这里的被驳回都是针对付款申请的付款、退款、异常结单申请被财务驳回的；付款申请单被驳回的都可以在这个里面查找，但是已完结驳回的是在已完结驳回列表里面；

**可申请退款：**是所有被驳回的付款申请单或采购单状态为质检审核中的付款申请单都是可以申请退款的；可以在这个状态列表里面找到需要的付款申请单申请退款；

**全额付款：**是所有已经全额付款的付款申请单，它的采购单也都全额付款了；

**部分付款：**是所有已经部分付款的付款申请单，该付款申请单中有一个或多个采购单部分付款的；

**需退款：**是付款申请单付款多付了，需要退款的付款申请单（这种状态的付款申请单，一般是付款申请单付完款后，又需要修改运费，如果修改运费金额比原运费金额小，这时，这个付款申请单就多付了，需要退款）；

**异常完成：**是所有已经异常完成的付款申请；

**全额退款：**是已付款后又全额退款的，这个一般最后都异常结单了；

**已申请退款：**是所有已经申请了退款的付款申请单；

**已申请异常结单：**是所有已经申请了异常结单的付款申请单，财务还没有操作确认异常结单的；

**已完结撤销付款：**是付款申请单已付款完成，但是又被撤销付款的（撤销付款是由财务操作的）；这种情况，采购可以再次申请付款、退款、或异常结单；

**已完结驳回：**是付款申请单已完成，然后财务又把它驳回的（这也是由财务直接操作的）；这种情况采购需要将它的采购单重新提交经理审核，财务再审核，再申请付款、退款或异常结单；

在【付款申请单】页面中，点击采购单号，可以**查看当前付款申请单的采购单明细信息**，如下图所示：

![](/assets/168import.png)

（查看付款申请的采购单明细信息）

**查看付款申请的付款记录**可以在付款申请单的右边点付款信息查看图标查看付款记录信息：

![](/assets/169import.png)

（查看付款申请单付款记录信息）

**【待申请付款的付款申请单申请付款】：**

![](/assets/170import.png)

（待申请付款的付款申请单再次申请付款）

待申请付款的付款申请单再次申请付款，其实就是付款申请单的二次付款，第一次只付了部分款项，后面又要付余下部分的款项，这就要进行二次付款了。

注意：在待申请付款状态列表中申请余下部分的付款时，如果此付款申请单有多个采购单，则如果其中一个采购单先前已全额付款，这次再申请付款时，这个采购单就不能再申请付款了，只能对先前部分付款的采购单再申请付款，在申请付款时，这个采购单的申请付款类型应该默认为部分付款的，申请付款金额 = 此采购单应付总金额 - 已部分付款的金额，申请付款金额一定不能大于此采购单余下未付款部分的金额，可以小于这个金额，小于这个金额就相当还需要申请一次付款或异常结单，才能完成这个付款申请单；

采购单应付总金额 = 采购单所有SKU总金额 + 运费 – 折扣金额

二次申请付款时，默认是以付款申请单的第一次付款方式付款的，如果二次付款需要改用其它的支付方式付款，可以修改付款方式，如下图所示：

![](/assets/171import.png)

由上图可以看到默认是以第一次付款方式付款，如果二次付款需要用其它支付方式付款，则可以修改付款方式，如所图所示：

![](/assets/172import.png)

![](/assets/173import.png)

（改用支付宝付款）

![](/assets/174import.png)

（增加其它银行的账号信息）

需不需要修改支付方式，按自己实际需要来确定，不需要改用其它支付方式就用默认的支付方式即可，不用修改；

【**已驳回的付款申请单的操作】：**

财务驳回的付款申请单如果没有付过款，则此付款申请单会被删除，采购单需要重新提交审核并根据实际需求再重新申请付款或申请异常结单；

![](/assets/175import.png)

（已驳回的付款申请单管理）

![](/assets/176import.png)

（已驳回的付款申请单修改采购单SKU价格和采购数量）

已驳回的付款、退款、异常结单申请单可以修改采购单SKU价格和采购数量，修改成功后采购单的总金额会变更，另外，此付款申请单的应付总金额也会根据修改的SKU价格和采购数量自动变更；

注意：

1、修改采购单SKU采购数量时，采购数量只能比原采购数量少，不能多；

2、**财务驳回的付款申请单如果没有付过款，则此付款申请单会被删除**，同时此付款申请单的采购单状态会变更为财务已驳回状态，这时这个付款申请单就不存在了，这个采购单就需要重新提交经理审核，然后再由财务审核，然后这个采购单又会到【待申请付款】列表里面去重新再申请付款或申请异常结单；

**财务驳回的付款申请单包括：付款申请驳回，退款申请驳回，异常结单申请驳回，已完结驳回；**

**【可申请退款的付款申请单操作申请退款】**

上面已经提到过申请退款分两种情况：一种：单纯申请一笔退款；另一种：申请退款并异常结单；

![](/assets/178import.png)

（可申请退款页面列表）

![](/assets/181import.png)

（可申请退款页面对付款申请单操作申请退款）

对付款申请单申请退款时，需要填写供应商那边的退款流水号，财务那边收到退款申请后，会根据这个退款流水号去查供应商的退款是否到账，如果查到退款已经到账号，财务那边就会操作确认退款，如果未查到退款，就会驳回退款申请；

一个付款申请单可能会有多个采购单，申请退款时，需要对哪个采购单申请退款就勾选这个采购单，并填写申请退款金额和退款备注，系统默认会自动计算显示申请退款的金额（这个申请退款金额采购自己可以手动填写或修改，系统默认自动计算的退款金额是根据此采购单的入库总金额和SKU总金额的差值计算的），退款金额如果觉得不对可以自行修改即可；

**退款并异常结单：**在对付款申请单申请退款时，如果想退款的同时并且异常结单，则可以勾选这个**“退款并异常结单”**，如果只想退一笔一款，不想结单，则不要勾选；勾选“退款并异常结单”申请退款后，财务确认退款之后，则这个付款申请单就会被退款并异常完成这个付款申请单；

【**部分付款申请单列表**】

（部分付款的付款申请单列表）

![](/assets/182import.png)

部分付款的付款申请单可以申请付款或**申请异常结单**；这里的申请付款和待申请付款列表里的付款申请单申请付款是一样的操作；

【**付款申请单申请异常结单】**

对付款申请单操作异常结单可以到部分付款列表中查找需要异常结单的付款申请单，然后按照步骤操作申请异常结单即可；

申请异常结单有两种，前面已经提到过，一种是在【可申请异常结单】列表中对未付款的采购单申请异常结单，另一种就是这里的对付款申请单申请异常结单；

![](/assets/183import.png)

（部分付款的申请单申请异常结单）

对付款申请单申请异常结单的操作和【可申请异常结单】里的对采购单申请异常结单差不多，只是说对付款申请单的异常结单编辑页面中增加了付款申请单的信息以及付款申请单的付款信息，以供参考使用；

同样的，付款申请单可能会有多个采购单，这里申请异常结单时，如果要对某个采购单的部分SKU申请异常结单，则只需要勾选这个SKU，并填写异常数量（系统默认计算的异常数量是根据SKU的已质检数量和采购数量的差值计算的，如果认为不正确可以自行修改，这里只是给一个参考的作用）和异常备注即可；如果需要对某个采购单整个异常结单，则不需要勾选SKU，只需勾选上面【结束采购单】中的需要结单的采购单，然后提交异常结单申请即可；

财务那边操作了确认异常结单申请之后，这个付款申请单就会被标记为异常完成的状态，同时申请异常结单的采购单会被标记为异常完成状态（注：如果没有勾选整个采购单异常结单则不会变更采购单状态）

**【已完结撤销付款列表】**

![](/assets/185import.png)

已完结撤销付款列表页面中可对付款申请单操作申请付款、退款、异常结单等；

这里的操作申请付款、退款、异常结单和上面其它地方操作申请付款、退款、异常结单是一样的，按照流程操作即可；

**【已完结驳回列表】**

已完结驳回列表里面的付款申请单也可以申请付款、退款、异常结单等操作，根据需要进行操作即可，操作方法也同上所示；

![](/assets/187import.png)

**4、采购单明细**

采购单明细列表页面是供采购查询所有自己的SKU的采购单以及采购助理绑定的供应商所有采购单下单信息的。因为实行按供应商下单后，有些SKU虽然属于自己的，但是该SKU的供应商有可能被其它采购助理所绑定，这样，这个SKU就会被其它采购助理所下单；另外，自己的SKU也可能会被自己的采购助理所下单，这时候查看这些SKU的下单情况就可以到这里查看了。

这个页面中的采购单信息是不可编辑或修改的，只能查看信息；

![](/assets/189import.png)

**【采购常见问题解答】**

1. **如何查找采购单：**

首先打开准采购单列表页面，在搜索条件中选择按“采购单号”查询，关键字输入框中输入采购单点，点查询，就可以查到这个采购单，如下图所示：

![](/assets/194import.png)

（选择搜索条件查询采购单）

找到采购单后，看采购单的状态，如下图所示：

![](/assets/191import.png)

看当前采购单是什么状态，然后就到准采购单的相应状态列表中去找到这个采购单，再做相应的操作就可以了。如上图所示，这个采购单的状态是“质检审核中”状态，那我们就可以去质检审核中列表中找到这个采购单，如果列表中采购单太单，就不要自己一行一行地找了，直接在这个状态下搜索这个采购单就可以了，这样省事，也更快。

上图中，采购单还有另外一个状态“付款申请单”，这个状态就说明了这个采购单已经申请付款了，而且生成了付款申请单；

采购单已有了付款申请单，那怎么查找采购单的付款申请单呢，同样的，很简单，就是到付款申请单列表中，在不选择任何状态的情况，选择按照采购单号查找付款申请单就可以了；

![](/assets/195import.png)

![](/assets/196import.png)

可以看到这就是我们要查找的付款申请单了。那为什么要在不选择状态情况下查找付款申请单呢，因为你只知道采购单号，不知道当前付款申请单是什么，也不知道付款申请单的状态，如果你在选择一个付款申请单状态的情况下查找这个付款申请单，它不一定能查到，因为这个付款申请单不一定是你选择的这个状态，所以要不选择状态来查找付款申请单，不选择状态的情况下查找，可以查找所有状态的付款申请单，这样必定会找到你需要的单，不会存在找不到单的情况。

在采购单或付款申请单很多的情况下，要会用查询功能来查找，定位又准确又快。

1. **采购单已有异常完成的情况下，由于供应商又来货了，需要仓库入库的解决办法：**

首先我们要明白，采购单在什么情况下是可以入库的，一般是在质检审核中的时候仓库那边是可以操作入库的，那我们采购单目前是异常完成，怎么让采购单状态变成质检审核中，那就是财务驳回单，采购单是财务驳回单状态下提交经理审核，财务审核通过后，采购单就变成质检审核中了，这样仓库就可以操作入库，所以解决办法就是让财务将采购单驳回成财务驳回单，这样就行了。

对于已付款的采购单，要想让采购单变成财务驳回单就需要到付款申请单中找到这个采购单的付款申请单，找财务驳回这个付款申请单，财务驳回后就可以操作了，

综上所述不管是什么情况下，只要我们了解最基本的流程，就知道该怎么处理采购单的任何解决问题了；

1. **关于供应商多发货，发错货的问题：**

公司的要求是我们采购单下的是什么产品，供应商就要按要求发什么货，发错码的，发错颜色的，是不让入库的，按公司的流程，就是把多发的退回，少发的让供应商补过来；

1. **采购单的付款申请单已经付款了，需要修改采购单信息的：**

对于已经付款的采购单，如果由于错误或其它原因需要修改价格或运费什么的，办法就是找财务驳回这个采购单的付款申请单，然后在付款申请单的已驳回、已完结驳回列表中找到这个付款申请单，点击“编辑”图标修改采购单信息，如果这个里面没有可修改的那就是不能修改；

1. **异常完成的采购单或付款申请单需要操作退款或付款：**

对于已经异常完成的采购单或付款申请单需要操作退款，解决办法就是让财务驳回这个付款申请单，然后就可以操作退款或付款了；

总之，大家记住一点，付款申请单状态为部分付款、已驳回、已完结驳回的付款申请单是可以申请付款、退款、异常结单的，大家如果想付款、退款或异常结单就想办法将付款申请单放入已驳回、已完结驳回列表中即可；

1. **什么样的采购单才算是已经完结的单：**

一个采购单既入库完成，又付款完成的才算是已完结的单了；那么入库完成就是指采购单的所有SKU都入库齐全，或采购单有异常完成；付款完成就是指采购单已经付款完毕，采购单的付款申请单已经全额付款或付款申请异常完成，这才算付款完毕，如果采购单的付款申请单状态是驳回状态（不管是哪种驳回）、需要退款状态、部分付款状态，待付款状态等等状态都是未付款完成，只有付款申请单状态是全额付款或异常完成状态才算付款完成，其它状态都不算；

1. **关于一个未付款就已经异常完成的采购单需要操作入库：**

对于一个未付款就已经异常完结的采购单，如果后来又来货了需要操作入库，这时候原采购单已经异常完结了，需要操作入库，解决办法就是：重新下一个采购单，然后入库付款即可；

