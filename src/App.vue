<template>
  <div class="all">
    <div class="withoutHeader">
      <div class="head">
        <div class="title">
          <!-- -->
          <a href="#" @click="main_show"
            ><img src="@/img/logo-gardena1.png" alt="gardena-logo" class="logo"
          /></a>
          <div class="cons" :class="isCalculator1Shown">
            <h1 class="consumption1">
              Потребление воды:
              <span :class="isOrangeRed1"> {{ currentConsumption1 }} </span> /
              <span class="totalcons"> {{ totalConsumption1 }}</span>
            </h1>
          </div>
          <div class="cons" :class="isCalculator2Shown">
            <h1 class="consumption2">
              Потребление воды:
              <span :class="isOrangeRed2"> {{ currentConsumption2 }} </span> /
              <span class="totalcons"> {{ totalConsumption2 }}</span>
            </h1>
          </div>
          <div class="cons" :class="isCalculator3Shown">
            <h1 class="consumption3">
              Потребление воды:
              <span :class="isOrangeRed3"> {{ currentConsumption3 }} </span> /
              <span class="totalcons"> {{ totalConsumption3 }}</span>
            </h1>
          </div>
        </div>
      </div>
      <div class="connection" :class="isMainShown">
        <div class="prechoose" :class="isMainShown">
          <h1 class="micro_drip_calculator">
            Калькулятор микрокапельного полива
          </h1>
        </div>
        <div class="choosing" :class="isMainShown">
          <h2 class="choose_your_type">Выберите тип подключения:</h2>
          <div class="choose row">
            <a href="#" @click="calc1_show">
              <div class="col install">
                <img class="installimg1" src="@/img/install1.jpg" alt="type1" />
                <!-- <h2 class="install_title">Тип подключения 1</h2>
              <div class="install_text">
                Снабжение водой начинается с магистрального шланга 13 мм.
                Капельницы установлены в подающий шланг 4.6 мм, который подводит
                воду от магистрального шланга к растениям.
              </div> -->
              </div>
            </a>
            <a href="#" @click="calc2_show">
              <div class="col install">
                <img class="installimg2" src="@/img/install2.jpg" alt="type1" />
                <!-- <h2 class="install_title">Тип подключения 2</h2>
              <div class="install_text">
                Снабжение водой начинается сразу с подающего шланга 4.6 мм без
                использования магистрального шланга. Длина такой линии полива не
                может превышать 15 метров.
              </div> -->
              </div>
            </a>
            <a href="#" @click="calc3_show">
              <div class="col install">
                <img class="installimg3" src="@/img/install3.jpg" alt="type1" />
                <!-- <h2 class="install_title">Тип подключения 3</h2>
              <div class="install_text">
                Снабжение водой производится только через магистральный шланг 13
                мм. Концевые капельницы, микронасадки, микродождеватели
                устанавливаются непосредственно в магистральный шланг.
              </div> -->
              </div>
            </a>
          </div>
        </div>
      </div>
      <div class="bg-white">
        <div class="micro_drip_calculator1" :class="isCalculator1Shown">
          <div class="row chooseMasterInstall_1">
            <div class="chooseMaster">
              <div class="row masterInstall">
                <div
                  class="master_1000_1"
                  @click="click_master_1000_1"
                  :class="isMaster_1000_1"
                >
                  Мастер-блок 1000
                </div>
                <div
                  class="master_2000_1"
                  @click="click_master_2000_1"
                  :class="isMaster_2000_1"
                >
                  Мастер-блок 2000
                </div>
              </div>
            </div>
            <div class="chooseInstallType">
              <div class="row masterInstall">
                <div
                  class="install_start_1"
                  @click="click_install_0_1"
                  :class="isCenter_0_1"
                >
                  В начале линии
                </div>
                <div
                  class="install_center_1"
                  @click="click_install_1_1"
                  :class="isCenter_1_1"
                >
                  В центре линии
                </div>
              </div>
            </div>
          </div>
          <!--
                    <div class="titles title1">Мастер-блок</div>
                        <div class="row drips">
                            <div class="col drip">
                                    <img class="dripimg" src="@/img/1340-29.png" alt="drip">
                                    <div class="row btns">
                                        <button class="minus" @click="minusm1340_1" :disabled='is1340_1'>-</button>
                                        <span class="span">{{ m1340_1 }}</span>
                                        <button class="plus" @click="plusm1340_1" :disabled='isMore1'>+</button>
                                        <h6>Капельница концевая<br>2 л/ч <span class="art">(арт.1340-29)</span></h6>
                                    </div>
                            </div>
                            <div class="col drip">
                                    <img class="dripimg" src="@/img/1341-29.png" alt="drip">
                                    <div class="row btns">
                                        <button class="minus" @click="minusm1341_1"  :disabled='is1341_1'>-</button>
                                        <span class="span"> {{ m1341_1 }} </span>
                                        <button class="plus" @click="plusm1341_1" :disabled='isMore1'>+</button>
                                        <h6>Капельница концевая<br>4 л/ч <span class="art">(арт.1341-29)</span></h6>                            
                                    </div>
                            </div>
                            <div class="col drip">
                                    <img class="dripimg" src="@/img/8310-29.png" alt="drip">
                                    <div class="row btns">
                                        <button class="minus" @click="minusm8310_1" :disabled='is8310_1'>-</button>
                                        <span class="span"> {{ m8310_1 }} </span>
                                        <button class="plus" @click="plusm8310_1" :disabled='isMore1'>+</button>
                                        <h6>Капельница концевая,<br>уравнивающая давление<br>2 л/ч<span class="art"> (арт.8310-29)</span></h6>
                                    </div>
                            </div>
                            <div class="col drip">
                                    <img class="dripimg" src="@/img/1391-29.png" alt="drip">

                            <div class="row btns">
                                        <button class="minus" @click="minusm1391_1" :disabled='is1391_1'>-</button>
                                        <span class="span"> {{ m1391_1 }} </span>
                                        <button class="plus" @click="plusm1391_1" :disabled='isMore1'>+</button>
                                        <h6>Капельница концевая,<br>регулируемая<br>0 - 20 л/ч<span class="art"> (арт.1391-29) *</span></h6>
                                    </div>
                            </div>
                            <div class="col drip">
                                    <img class="dripimg" src="@/img/8316-29.png" alt="drip">
                                    <div class="row btns">
                                        <button class="minus" @click="minusm8316_1" :disabled='is8316_1'>-</button>
                                        <span class="span"> {{ m8316_1 }} </span>
                                        <button class="plus" @click="plusm8316_1" :disabled='isMore1'>+</button>
                                        <h6>Капельница концевая,<br>уравнивающая давление<br>1 - 8 л/ч<span class="art"> (арт.8316-29)</span></h6>
                                    </div>
                            </div>
                        </div>

                        -->

          <div class="titles title1">Капельницы концевые</div>
          <div class="row drips">
            <div class="col drip">
              <img class="dripimg" src="@/img/1340-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1340_1"
                  :disabled="is1340_1"
                >
                  -
                </button>
                <span class="span">{{ m1340_1 }}</span>
                <button class="plus" @click="plusm1340_1" :disabled="isMore1">
                  +
                </button>
                <h6>
                  Капельница концевая<br />2 л/ч
                  <span class="art">(арт.1340-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/1341-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1341_1"
                  :disabled="is1341_1"
                >
                  -
                </button>
                <span class="span"> {{ m1341_1 }} </span>
                <button class="plus" @click="plusm1341_1" :disabled="isMore1">
                  +
                </button>
                <h6>
                  Капельница концевая<br />4 л/ч
                  <span class="art">(арт.1341-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/8310-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm8310_1"
                  :disabled="is8310_1"
                >
                  -
                </button>
                <span class="span"> {{ m8310_1 }} </span>
                <button class="plus" @click="plusm8310_1" :disabled="isMore1">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />уравнивающая давление<br />2
                  л/ч<span class="art"> (арт.8310-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/1391-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1391_1"
                  :disabled="is1391_1"
                >
                  -
                </button>
                <span class="span"> {{ m1391_1 }} </span>
                <button class="plus" @click="plusm1391_1" :disabled="isMore1">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />регулируемая<br />0 - 20 л/ч<span
                    class="art"
                  >
                    (арт.1391-29) *</span
                  >
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/8316-29.png" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm8316_1"
                  :disabled="is8316_1"
                >
                  -
                </button>
                <span class="span"> {{ m8316_1 }} </span>
                <button class="plus" @click="plusm8316_1" :disabled="isMore1">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />уравнивающая давление<br />1 - 8
                  л/ч<span class="art"> (арт.8316-29)</span>
                </h6>
              </div>
            </div>
          </div>
          <div>
            <div class="titles title2">Капельницы внутренние</div>
            <div class="row drips">
              <div class="col drip">
                <img class="dripimg" src="@/img/8343-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8343_1"
                    :disabled="is8343_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8343_1 }} </span>
                  <button class="plus" @click="plusm8343_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />2 л/ч<span class="art">
                      (арт.8343-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8344-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8344_1"
                    :disabled="is8344_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8344_1 }} </span>
                  <button class="plus" @click="plusm8344_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />4 л/ч<span class="art">
                      (арт.8344-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8311-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8311_1"
                    :disabled="is8311_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8311_1 }} </span>
                  <button class="plus" @click="plusm8311_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />уравнивающая давление<br />2 л/ч
                    <span class="art">(арт.8311-29)</span>
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8392-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8392_1"
                    :disabled="is8392_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8392_1 }} </span>
                  <button class="plus" @click="plusm8392_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />регулируемая<br /><span
                      class="art"
                      >(арт.8392-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8317-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8317_1"
                    :disabled="is8317_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8317_1 }} </span>
                  <button class="plus" @click="plusm8317_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />уравнивающая давление<br /><span
                      class="art"
                      >(арт.8317-29)</span
                    >
                  </h6>
                </div>
              </div>
            </div>
          </div>
          <div>
            <div class="titles title3">Микронасадки</div>
            <div class="row drips">
              <div class="col drip">
                <img class="dripimg" src="@/img/1370-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1370_1"
                    :disabled="is1370_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1370_1 }} </span>
                  <button class="plus" @click="plusm1370_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Микронасадка ленточная<br /><span class="art"
                      >(арт.1370-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1372-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1372_1"
                    :disabled="is1372_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1372_1 }} </span>
                  <button class="plus" @click="plusm1372_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Микронасадка ленточная<br /><span class="art"
                      >(арт.1372-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1368-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1368_1"
                    :disabled="is1368_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1368_1 }} </span>
                  <button class="plus" @click="plusm1368_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Микронасадка 90&deg<br /><span class="art"
                      >(арт.1368-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1367-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1367_1"
                    :disabled="is1367_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1367_1 }} </span>
                  <button class="plus" @click="plusm1367_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Микронасадка 180&deg<br /><span class="art"
                      >(арт.1367-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1365-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1365_1"
                    :disabled="is1365_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1365_1 }} </span>
                  <button class="plus" @click="plusm1365_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Микронасадка 360&deg<br /><span class="art"
                      >(арт.1365-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1371-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1371_1"
                    :disabled="is1371_1"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1371_1 }} </span>
                  <button class="plus" @click="plusm1371_1" :disabled="isMore1">
                    +
                  </button>
                  <h6>
                    Микронасадка распыляющая<br /><span class="art"
                      >(арт.1371-29)</span
                    >
                  </h6>
                </div>
              </div>
            </div>
            <div>
              <div>
                <div class="titles title4">Микродождеватели</div>
                <div class="row drips">
                  <div class="col drip">
                    <img class="dripimg" src="@/img/8321-29.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm8321_1"
                        :disabled="is8321_1"
                      >
                        -
                      </button>
                      <span class="span"> {{ m8321_1 }} </span>
                      <button
                        class="plus"
                        @click="plusm8321_1"
                        :disabled="isMore1"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель внутренний<br />для малых площадей<br /><span
                          class="art"
                          >(арт.8321-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1396-29.webp" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1396_1"
                        :disabled="is1396_1"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1396_1 }} </span>
                      <button
                        class="plus"
                        @click="plusm1396_1"
                        :disabled="isMore1"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />шестипозиционный<br /><span
                          class="art"
                          >(арт.1396-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1369-29.jpg" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1369_1"
                        :disabled="is1369_1"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1369_1 }} </span>
                      <button
                        class="plus"
                        @click="plusm1369_1"
                        :disabled="isMore1"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />круговой<br /><span class="art"
                          >(арт.1369-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                </div>
              </div>
              <div>
                <div class="titles title5">Шланги сочащиеся</div>
                <div class="row drips">
                  <div class="col drip">
                    <img class="dripimg" src="@/img/13010.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm13010_1"
                        :disabled="is13010_1"
                      >
                        -
                      </button>
                      <span class="span"> {{ m13010_1 }} </span>
                      <button
                        class="plus"
                        @click="plusm13010_1"
                        :disabled="isMore1"
                      >
                        +
                      </button>
                      <h6>
                        Комплект базовый<br />для наземной прокладки<br />4.6 мм
                        <span class="art">(арт.13010-20)</span><br />
                        1 метр
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1362.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1362_1"
                        :disabled="is1362_1"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1362_1 }} </span>
                      <button
                        class="plus"
                        @click="plusm1362_1"
                        :disabled="isMore1"
                      >
                        +
                      </button>
                      <h6>
                        Шланг сочащийся<br />для наземной прокладки<br />4.6
                        мм<span class="art">(арт.1362-20)</span><br />
                        1 метр
                      </h6>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- Calculatior of the second type -->
        <div class="micro_drip_calculator2" :class="isCalculator2Shown">
          <div class="px80"></div>

          <div class="row chooseMasterInstall_2">
            <div class="chooseMaster">
              <div class="row masterInstall">
                <div
                  class="master_1000_2"
                  @click="click_master_1000_2"
                  :class="isMaster_1000_2"
                >
                  Мастер-блок 1000
                </div>
                <div
                  class="master_2000_2"
                  @click="click_master_2000_2"
                  :class="isMaster_2000_2"
                >
                  Мастер-блок 2000
                </div>
              </div>
            </div>
            <div class="chooseInstallType">
              <div class="row masterInstall">
                <div
                  class="install_start_2"
                  @click="click_install_0_2"
                  :class="isCenter_0_2"
                >
                  В начале линии
                </div>
                <div
                  class="install_center_2"
                  @click="click_install_1_2"
                  :class="isCenter_1_2"
                >
                  В центре линии
                </div>
              </div>
            </div>
          </div>

          <div class="titles title1">Капельницы концевые</div>
          <div class="row drips">
            <div class="col drip">
              <img class="dripimg" src="@/img/1340-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1340_2"
                  :disabled="is1340_2"
                >
                  -
                </button>
                <span class="span">{{ m1340_2 }}</span>
                <button class="plus" @click="plusm1340_2" :disabled="isMore2">
                  +
                </button>
                <h6>
                  Капельница концевая<br />2 л/ч
                  <span class="art">(арт.1340-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/1341-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1341_2"
                  :disabled="is1341_2"
                >
                  -
                </button>
                <span class="span"> {{ m1341_2 }} </span>
                <button class="plus" @click="plusm1341_2" :disabled="isMore2">
                  +
                </button>
                <h6>
                  Капельница концевая<br />4 л/ч
                  <span class="art">(арт.1341-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/8310-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm8310_2"
                  :disabled="is8310_2"
                >
                  -
                </button>
                <span class="span"> {{ m8310_2 }} </span>
                <button class="plus" @click="plusm8310_2" :disabled="isMore2">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />уравнивающая давление<br />2
                  л/ч<span class="art"> (арт.8310-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/1391-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1391_2"
                  :disabled="is1391_2"
                >
                  -
                </button>
                <span class="span"> {{ m1391_2 }} </span>
                <button class="plus" @click="plusm1391_2" :disabled="isMore2">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />регулируемая<br />0 - 20 л/ч<span
                    class="art"
                  >
                    (арт.1391-29) *</span
                  >
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/8316-29.png" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm8316_2"
                  :disabled="is8316_2"
                >
                  -
                </button>
                <span class="span"> {{ m8316_2 }} </span>
                <button class="plus" @click="plusm8316_2" :disabled="isMore2">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />уравнивающая давление<br />1 - 8
                  л/ч<span class="art"> (арт.8316-29)</span>
                </h6>
              </div>
            </div>
          </div>
          <div>
            <div class="titles title2">Капельницы внутренние</div>
            <div class="row drips">
              <div class="col drip">
                <img class="dripimg" src="@/img/8343-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8343_2"
                    :disabled="is8343_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8343_2 }} </span>
                  <button class="plus" @click="plusm8343_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />2 л/ч<span class="art">
                      (арт.8343-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8344-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8344_2"
                    :disabled="is8344_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8344_2 }} </span>
                  <button class="plus" @click="plusm8344_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />4 л/ч<span class="art">
                      (арт.8344-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8311-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8311_2"
                    :disabled="is8311_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8311_2 }} </span>
                  <button class="plus" @click="plusm8311_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />уравнивающая давление<br />2 л/ч
                    <span class="art">(арт.8311-29)</span>
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8392-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8392_2"
                    :disabled="is8392_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8392_2 }} </span>
                  <button class="plus" @click="plusm8392_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />регулируемая<br /><span
                      class="art"
                      >(арт.8392-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/8317-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm8317_2"
                    :disabled="is8317_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m8317_2 }} </span>
                  <button class="plus" @click="plusm8317_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Капельница внутренняя<br />уравнивающая давление<br /><span
                      class="art"
                      >(арт.8317-29)</span
                    >
                  </h6>
                </div>
              </div>
            </div>
          </div>
          <div>
            <div class="titles title3">Микронасадки</div>
            <div class="row drips">
              <div class="col drip">
                <img class="dripimg" src="@/img/1370-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1370_2"
                    :disabled="is1370_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1370_2 }} </span>
                  <button class="plus" @click="plusm1370_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Микронасадка ленточная<br /><span class="art"
                      >(арт. 1370-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1372-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1372_2"
                    :disabled="is1372_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1372_2 }} </span>
                  <button class="plus" @click="plusm1372_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Микронасадка ленточная<br /><span class="art"
                      >(арт.1372-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1368-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1368_2"
                    :disabled="is1368_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1368_2 }} </span>
                  <button class="plus" @click="plusm1368_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Микронасадка 90&deg<br /><span class="art"
                      >(арт.1368-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1367-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1367_2"
                    :disabled="is1367_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1367_2 }} </span>
                  <button class="plus" @click="plusm1367_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Микронасадка 180&deg<br /><span class="art"
                      >(арт.1367-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1365-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1365_2"
                    :disabled="is1365_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1365_2 }} </span>
                  <button class="plus" @click="plusm1365_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Микронасадка 360&deg<br /><span class="art"
                      >(арт.1365-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img
                  class="dripimg micronasadka"
                  src="@/img/1371-29.jpg"
                  alt="drip"
                />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1371_2"
                    :disabled="is1371_2"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1371_2 }} </span>
                  <button class="plus" @click="plusm1371_2" :disabled="isMore2">
                    +
                  </button>
                  <h6>
                    Микронасадка распыляющая<br /><span class="art"
                      >(арт.1371-29)</span
                    >
                  </h6>
                </div>
              </div>
            </div>
            <div>
              <div>
                <div class="titles title4">Дождеватели и микродождеватели</div>
                <div class="row drips">
                  <div class="col drip">
                    <img class="dripimg" src="@/img/8321-29.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm8321_2"
                        :disabled="is8321_2"
                      >
                        -
                      </button>
                      <span class="span"> {{ m8321_2 }} </span>
                      <button
                        class="plus"
                        @click="plusm8321_2"
                        :disabled="isMore2"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель внутренний<br />для малых площадей<br /><span
                          class="art"
                          >(арт.8321-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1396-29.webp" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1396_2"
                        :disabled="is1396_2"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1396_2 }} </span>
                      <button
                        class="plus"
                        @click="plusm1396_2"
                        :disabled="isMore2"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />шестипозиционный<br /><span
                          class="art"
                          >(арт.1396-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1369-29.jpg" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1369_2"
                        :disabled="is1369_2"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1369_2 }} </span>
                      <button
                        class="plus"
                        @click="plusm1369_2"
                        :disabled="isMore2"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />круговой<br /><span class="art"
                          >(арт.1369-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                </div>
              </div>

              <div>
                <div class="titles title5">Шланги сочащиеся</div>
                <div class="row drips">
                  <div class="col drip">
                    <img class="dripimg" src="@/img/13010.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm13010_2"
                        :disabled="is13010_2"
                      >
                        -
                      </button>
                      <span class="span"> {{ m13010_2 }} </span>
                      <button
                        class="plus"
                        @click="plusm13010_2"
                        :disabled="isMore2"
                      >
                        +
                      </button>
                      <h6>
                        Комплект базовый<br />для наземной прокладки<br />4.6 мм
                        <span class="art">(арт.13010-20)</span><br />
                        1 метр
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1362.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1362_2"
                        :disabled="is1362_2"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1362_2 }} </span>
                      <button
                        class="plus"
                        @click="plusm1362_2"
                        :disabled="isMore2"
                      >
                        +
                      </button>
                      <h6>
                        Шланг сочащийся<br />для наземной прокладки<br />4.6
                        мм<span class="art">(арт.1362-20)</span><br />
                        1 метр
                      </h6>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Calculator of the 3rd type -->
        <div class="micro_drip_calculator3" :class="isCalculator3Shown">
          <div class="px80"></div>
          <div class="row chooseMasterInstall_3">
            <div class="chooseMaster">
              <div class="row masterInstall">
                <div
                  class="master_1000_3"
                  @click="click_master_1000_3"
                  :class="isMaster_1000_3"
                >
                  Мастер-блок 1000
                </div>
                <div
                  class="master_2000_3"
                  @click="click_master_2000_3"
                  :class="isMaster_2000_3"
                >
                  Мастер-блок 2000
                </div>
              </div>
            </div>
            <div class="chooseInstallType">
              <div class="row masterInstall">
                <div
                  class="install_start_3"
                  @click="click_install_0_3"
                  :class="isCenter_0_3"
                >
                  В начале линии
                </div>
                <div
                  class="install_center_3"
                  @click="click_install_1_3"
                  :class="isCenter_1_3"
                >
                  В центре линии
                </div>
              </div>
            </div>
          </div>

          <div class="titles title1">Капельницы концевые</div>
          <div class="row drips">
            <div class="col drip">
              <img class="dripimg" src="@/img/1340-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1340_3"
                  :disabled="is1340_3"
                >
                  -
                </button>
                <span class="span">{{ m1340_3 }}</span>
                <button class="plus" @click="plusm1340_3" :disabled="isMore3">
                  +
                </button>
                <h6>
                  Капельница концевая<br />2 л/ч
                  <span class="art">(арт.1340-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/1341-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1341_3"
                  :disabled="is1341_3"
                >
                  -
                </button>
                <span class="span"> {{ m1341_3 }} </span>
                <button class="plus" @click="plusm1341_3" :disabled="isMore3">
                  +
                </button>
                <h6>
                  Капельница концевая<br />4 л/ч
                  <span class="art">(арт.1341-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/8310-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm8310_3"
                  :disabled="is8310_3"
                >
                  -
                </button>
                <span class="span"> {{ m8310_3 }} </span>
                <button class="plus" @click="plusm8310_3" :disabled="isMore3">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />уравнивающая давление<br />2
                  л/ч<span class="art"> (арт.8310-29)</span>
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/1391-29.jpg" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm1391_3"
                  :disabled="is1391_3"
                >
                  -
                </button>
                <span class="span"> {{ m1391_3 }} </span>
                <button class="plus" @click="plusm1391_3" :disabled="isMore3">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />регулируемая<br />0 - 20 л/ч<span
                    class="art"
                  >
                    (арт.1391-29)</span
                  >
                </h6>
              </div>
            </div>
            <div class="col drip">
              <img class="dripimg" src="@/img/8316-29.png" alt="drip" />
              <div class="row btns">
                <button
                  class="minus"
                  @click="minusm8316_3"
                  :disabled="is8316_3"
                >
                  -
                </button>
                <span class="span"> {{ m8316_3 }} </span>
                <button class="plus" @click="plusm8316_3" :disabled="isMore3">
                  +
                </button>
                <h6>
                  Капельница концевая,<br />уравнивающая давление<br />1 - 8
                  л/ч<span class="art"> (арт.8316-29)</span>
                </h6>
              </div>
            </div>
          </div>
          <div>
            <div class="titles title3">Микронасадки</div>
            <div class="row drips">
              <div class="col drip">
                <img class="dripimg" src="@/img/1370-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1370_3"
                    :disabled="is1370_3"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1370_3 }} </span>
                  <button class="plus" @click="plusm1370_3" :disabled="isMore3">
                    +
                  </button>
                  <h6>
                    Микронасадка ленточная<br /><span class="art"
                      >(арт.1370-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1372-29.png" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1372_3"
                    :disabled="is1372_3"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1372_3 }} </span>
                  <button class="plus" @click="plusm1372_3" :disabled="isMore3">
                    +
                  </button>
                  <h6>
                    Микронасадка ленточная<br /><span class="art"
                      >(арт.1372-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1368-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1368_3"
                    :disabled="is1368_3"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1368_3 }} </span>
                  <button class="plus" @click="plusm1368_3" :disabled="isMore3">
                    +
                  </button>
                  <h6>
                    Микронасадка 90&deg<br /><span class="art"
                      >(арт.1368-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1367-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1367_3"
                    :disabled="is1367_3"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1367_3 }} </span>
                  <button class="plus" @click="plusm1367_3" :disabled="isMore3">
                    +
                  </button>
                  <h6>
                    Микронасадка 180&deg<br /><span class="art"
                      >(арт.1367-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1365-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1365_3"
                    :disabled="is1365_3"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1365_3 }} </span>
                  <button class="plus" @click="plusm1365_3" :disabled="isMore3">
                    +
                  </button>
                  <h6>
                    Микронасадка 360&deg<br /><span class="art"
                      >(арт.1365-29)</span
                    >
                  </h6>
                </div>
              </div>
              <div class="col drip">
                <img class="dripimg" src="@/img/1371-29.jpg" alt="drip" />
                <div class="row btns">
                  <button
                    class="minus"
                    @click="minusm1371_3"
                    :disabled="is1371_3"
                  >
                    -
                  </button>
                  <span class="span"> {{ m1371_3 }} </span>
                  <button class="plus" @click="plusm1371_3" :disabled="isMore3">
                    +
                  </button>
                  <h6>
                    Микронасадка распыляющая<br /><span class="art"
                      >(арт.1371-29)</span
                    >
                  </h6>
                </div>
              </div>
            </div>
            <div>
              <div>
                <div class="titles title4">Дождеватели и микродождеватели</div>
                <div class="row drips">
                  <div class="col drip">
                    <img class="dripimg" src="@/img/8320-29.jpg" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm8320_3"
                        :disabled="is8320_3"
                      >
                        -
                      </button>
                      <span class="span"> {{ m8320_3 }} </span>
                      <button
                        class="plus"
                        @click="plusm8320_3"
                        :disabled="isMore3"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />для малых площадей<br /><span
                          class="art"
                          >(арт.8320-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1396-29.webp" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1396_3"
                        :disabled="is1396_3"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1396_3 }} </span>
                      <button
                        class="plus"
                        @click="plusm1396_3"
                        :disabled="isMore3"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />шестипозиционный<br /><span
                          class="art"
                          >(арт.1396-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/1369-29.jpg" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm1369_3"
                        :disabled="is1369_3"
                      >
                        -
                      </button>
                      <span class="span"> {{ m1369_3 }} </span>
                      <button
                        class="plus"
                        @click="plusm1369_3"
                        :disabled="isMore3"
                      >
                        +
                      </button>
                      <h6>
                        Микродождеватель<br />круговой<br /><span class="art"
                          >(арт.1369-29)</span
                        >
                      </h6>
                    </div>
                  </div>
                  <div class="col drip">
                    <img class="dripimg" src="@/img/8364-20.webp" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm8364_3"
                        :disabled="is8364_3"
                      >
                        -
                      </button>
                      <span class="span"> {{ m8364_3 }} </span>
                      <button
                        class="plus"
                        @click="plusm8364_3"
                        :disabled="isMore3"
                      >
                        +
                      </button>
                      <h6>
                        Дождеватель<br />осциллирующий OS 90<br /><span
                          class="art"
                          >(арт.8364-20)</span
                        >
                      </h6>
                    </div>
                  </div>
                </div>
                <div class="titles title5">Шланги сочащиеся</div>
                <div class="row drips">
                  <div class="col drip">
                    <img class="dripimg" src="@/img/13013.png" alt="drip" />
                    <div class="row btns">
                      <button
                        class="minus"
                        @click="minusm13013_3"
                        :disabled="is13013_3"
                      >
                        -
                      </button>
                      <span class="span"> {{ m13013_3 }} </span>
                      <button
                        class="plus"
                        @click="plusm13013_3"
                        :disabled="isMore3"
                      >
                        +
                      </button>
                      <h6>
                        Шланг сочащийся<br />для наземной прокладки<br />13 мм
                        <span class="art">(арт.13013-20)</span><br />
                        1 метр
                      </h6>
                    </div>
                  </div>
                </div>
              </div>
              <div></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mainpage: 1,
      typeone: 0,
      typetwo: 0,
      typethree: 0,
      currentConsumption1: 0,
      currentConsumption2: 0,
      currentConsumption3: 0,
      totalConsumption1: 2000,
      totalConsumption2: 100,
      totalConsumption3: 2000,
      master_1: 2000,
      center_1: 1,
      master_2: 2000,
      center_2: 1,
      master_3: 2000,
      center_3: 1,
      m1340_1: 0,
      m1341_1: 0,
      m8310_1: 0,
      m1391_1: 0,
      m8316_1: 0,
      m8343_1: 0,
      m8344_1: 0,
      m8311_1: 0,
      m8392_1: 0,
      m8317_1: 0,
      m1370_1: 0,
      m1372_1: 0,
      m1368_1: 0,
      m1367_1: 0,
      m1365_1: 0,
      m1371_1: 0,
      m8320_1: 0,
      m8321_1: 0,
      m1396_1: 0,
      m1369_1: 0,
      m8364_1: 0,
      m13010_1: 0,
      m1362_1: 0,
      m1340_2: 0,
      m1341_2: 0,
      m8310_2: 0,
      m1391_2: 0,
      m8316_2: 0,
      m8343_2: 0,
      m8344_2: 0,
      m8311_2: 0,
      m8392_2: 0,
      m8317_2: 0,
      m1370_2: 0,
      m1372_2: 0,
      m1368_2: 0,
      m1367_2: 0,
      m1365_2: 0,
      m1371_2: 0,
      m8320_2: 0,
      m8321_2: 0,
      m1396_2: 0,
      m1369_2: 0,
      m8364_2: 0,
      m13010_2: 0,
      m1362_2: 0,
      m1340_3: 0,
      m1341_3: 0,
      m8310_3: 0,
      m1391_3: 0,
      m8316_3: 0,
      m8343_3: 0,
      m8344_3: 0,
      m8311_3: 0,
      m8392_3: 0,
      m8317_3: 0,
      m1370_3: 0,
      m1372_3: 0,
      m1368_3: 0,
      m1367_3: 0,
      m1365_3: 0,
      m1371_3: 0,
      m8320_3: 0,
      m8321_3: 0,
      m1396_3: 0,
      m1369_3: 0,
      m8364_3: 0,
      m13001_3: 0,
      m13002_3: 0,
      m13013_3: 0,
    };
  },
  computed: {
    isOrangeRed1: function () {
      return {
        orangered: this.currentConsumption1 > this.totalConsumption1,
      };
    },
    isOrangeRed2: function () {
      return {
        orangered: this.currentConsumption2 > this.totalConsumption2,
      };
    },
    isOrangeRed3: function () {
      return {
        orangered: this.currentConsumption3 > this.totalConsumption3,
      };
    },
    isCalculator1Shown: function () {
      return {
        hide: this.typeone === 0,
      };
    },
    isCalculator2Shown: function () {
      return {
        hide: this.typetwo === 0,
      };
    },
    isCalculator3Shown: function () {
      return {
        hide: this.typethree === 0,
      };
    },
    isMainShown: function () {
      return {
        hide: this.mainpage === 0,
      };
    },
    isMore1: function () {
      return this.currentConsumption1 >= this.totalConsumption1;
    },
    isMore2: function () {
      return this.currentConsumption2 >= this.totalConsumption2;
    },
    isMore3: function () {
      return this.currentConsumption3 >= this.totalConsumption3;
    },
    isMaster_1000_1: function () {
      return {
        teal: this.master_1 === 1000,
      };
    },
    isMaster_2000_1: function () {
      return {
        teal: this.master_1 === 2000,
      };
    },
    isCenter_0_1: function () {
      return {
        teal: this.center_1 === 0,
      };
    },
    isCenter_1_1: function () {
      return {
        teal: this.center_1 === 1,
      };
    },

    isMaster_1000_2: function () {
      return {
        teal: this.master_2 === 1000,
      };
    },
    isMaster_2000_2: function () {
      return {
        teal: this.master_2 === 2000,
      };
    },
    isCenter_0_2: function () {
      return {
        teal: this.center_2 === 0,
      };
    },
    isCenter_1_2: function () {
      return {
        teal: this.center_2 === 1,
      };
    },

    isMaster_1000_3: function () {
      return {
        teal: this.master_3 === 1000,
      };
    },
    isMaster_2000_3: function () {
      return {
        teal: this.master_3 === 2000,
      };
    },
    isCenter_0_3: function () {
      return {
        teal: this.center_3 === 0,
      };
    },
    isCenter_1_3: function () {
      return {
        teal: this.center_3 === 1,
      };
    },

    is1340_1() {
      return this.m1340_1 === 0;
    },
    is1341_1() {
      return this.m1341_1 === 0;
    },
    is8310_1() {
      return this.m8310_1 === 0;
    },
    is1391_1() {
      return this.m1391_1 === 0;
    },
    is8316_1() {
      return this.m8316_1 === 0;
    },
    is8343_1() {
      return this.m8343_1 === 0;
    },
    is8344_1() {
      return this.m8344_1 === 0;
    },
    is8311_1() {
      return this.m8311_1 === 0;
    },
    is8392_1() {
      return this.m8311_1 === 0;
    },
    is8317_1() {
      return this.m8317_1 === 0;
    },
    is1370_1() {
      return this.m1370_1 === 0;
    },
    is1372_1() {
      return this.m1372_1 === 0;
    },
    is1368_1() {
      return this.m1368_1 === 0;
    },
    is1367_1() {
      return this.m1367_1 === 0;
    },
    is1365_1() {
      return this.m1365_1 === 0;
    },
    is1371_1() {
      return this.m1371_1 === 0;
    },
    is8321_1() {
      return this.m8321_1 === 0;
    },
    is1396_1() {
      return this.m1396_1 === 0;
    },
    is1369_1() {
      return this.m1369_1 === 0;
    },
    is13010_1() {
      return this.m13010_1 === 0;
    },
    is1362_1() {
      return this.m1362_1 === 0;
    },
    is1340_2() {
      return this.m1340_2 === 0;
    },
    is1341_2() {
      return this.m1341_2 === 0;
    },
    is8310_2() {
      return this.m8310_2 === 0;
    },
    is1391_2() {
      return this.m1391_2 === 0;
    },
    is8316_2() {
      return this.m8316_2 === 0;
    },
    is8343_2() {
      return this.m8343_2 === 0;
    },
    is8344_2() {
      return this.m8344_2 === 0;
    },
    is8311_2() {
      return this.m8311_2 === 0;
    },
    is8392_2() {
      return this.m8311_2 === 0;
    },
    is8317_2() {
      return this.m8317_2 === 0;
    },
    is1370_2() {
      return this.m1370_2 === 0;
    },
    is1372_2() {
      return this.m1372_2 === 0;
    },
    is1368_2() {
      return this.m1368_2 === 0;
    },
    is1367_2() {
      return this.m1367_2 === 0;
    },
    is1365_2() {
      return this.m1365_2 === 0;
    },
    is1371_2() {
      return this.m1371_2 === 0;
    },
    is8321_2() {
      return this.m8321_2 === 0;
    },
    is1396_2() {
      return this.m1396_2 === 0;
    },
    is1369_2() {
      return this.m1369_2 === 0;
    },
    is13010_2() {
      return this.m13010_2 === 0;
    },
    is1362_2() {
      return this.m1362_2 === 0;
    },
    is1340_3() {
      return this.m1340_3 === 0;
    },
    is1341_3() {
      return this.m1341_3 === 0;
    },
    is8310_3() {
      return this.m8310_3 === 0;
    },
    is1391_3() {
      return this.m1391_3 === 0;
    },
    is8316_3() {
      return this.m8316_3 === 0;
    },
    is1370_3() {
      return this.m1370_3 === 0;
    },
    is1372_3() {
      return this.m1372_3 === 0;
    },
    is1368_3() {
      return this.m1368_3 === 0;
    },
    is1367_3() {
      return this.m1367_3 === 0;
    },
    is1365_3() {
      return this.m1365_3 === 0;
    },
    is1371_3() {
      return this.m1371_3 === 0;
    },
    is8320_3() {
      return this.m8320_3 === 0;
    },
    is1396_3() {
      return this.m1396_3 === 0;
    },
    is1369_3() {
      return this.m1369_3 === 0;
    },
    is8364_3() {
      return this.m8364_3 === 0;
    },
    is13013_3() {
      return this.m13013_3 === 0;
    },
  },
  methods: {
    click_master_1000_1() {
      this.center_1 === 0
        ? (this.totalConsumption1 = 500)
        : (this.totalConsumption1 = 1000);
      this.master_1 = 1000;
    },
    click_master_2000_1() {
      this.center_1 === 1
        ? (this.totalConsumption1 = 2000)
        : (this.totalConsumption1 = 1000);
      this.master_1 = 2000;
    },
    click_install_0_1() {
      this.master_1 === 1000
        ? (this.totalConsumption1 = 500)
        : (this.totalConsumption1 = 1000);
      this.center_1 = 0;
    },
    click_install_1_1() {
      this.master_1 === 2000
        ? (this.totalConsumption1 = 2000)
        : (this.totalConsumption1 = 1000);
      this.center_1 = 1;
    },

    click_master_1000_2() {
      this.center_2 === 0
        ? (this.totalConsumption2 = 50)
        : (this.totalConsumption2 = 100);
      this.master_2 = 1000;
    },
    click_master_2000_2() {
      this.center_2 === 1
        ? (this.totalConsumption2 = 100)
        : (this.totalConsumption2 = 50);
      this.master_2 = 2000;
    },
    click_install_0_2() {
      this.master_2 === 1000
        ? (this.totalConsumption2 = 50)
        : (this.totalConsumption2 = 50);
      this.center_2 = 0;
    },
    click_install_1_2() {
      this.master_2 === 2000
        ? (this.totalConsumption2 = 100)
        : (this.totalConsumption2 = 100);
      this.center_2 = 1;
    },

    click_master_1000_3() {
      this.center_3 === 0
        ? (this.totalConsumption3 = 500)
        : (this.totalConsumption3 = 1000);
      this.master_3 = 1000;
    },
    click_master_2000_3() {
      this.center_3 === 1
        ? (this.totalConsumption3 = 2000)
        : (this.totalConsumption3 = 1000);
      this.master_3 = 2000;
    },
    click_install_0_3() {
      this.master_3 === 1000
        ? (this.totalConsumption3 = 500)
        : (this.totalConsumption3 = 1000);
      this.center_3 = 0;
    },
    click_install_1_3() {
      this.master_3 === 2000
        ? (this.totalConsumption3 = 2000)
        : (this.totalConsumption3 = 1000);
      this.center_3 = 1;
    },

    main_page_show() {
      this.mainpage = 1;
    },
    main_page_hide() {
      this.mainpage = 0;
    },
    type_one_show() {
      this.typeone = 1;
    },
    type_one_hide() {
      this.typeone = 0;
    },
    type_two_show() {
      this.typetwo = 1;
    },
    type_two_hide() {
      this.typetwo = 0;
    },
    type_three_show() {
      this.typethree = 1;
    },
    type_three_hide() {
      this.typethree = 0;
    },
    main_show() {
      this.mainpage = 1;
      this.typetwo = 0;
      this.typethree = 0;
      this.typeone = 0;
    },
    calc1_show() {
      this.mainpage = 0;
      this.typetwo = 0;
      this.typethree = 0;
      this.typeone = 1;
    },
    calc2_show() {
      this.mainpage = 0;
      this.typetwo = 1;
      this.typethree = 0;
      this.typeone = 0;
    },
    calc3_show() {
      this.mainpage = 0;
      this.typetwo = 0;
      this.typethree = 1;
      this.typeone = 0;
    },
    plusm1340_1() {
      this.m1340_1 += 1;
      this.currentConsumption1 += 2;
    },
    minusm1340_1() {
      this.m1340_1 -= 1;
      this.currentConsumption1 -= 2;
    },
    plusm1341_1() {
      this.m1341_1 += 1;
      this.currentConsumption1 += 4;
    },
    minusm1341_1() {
      this.m1341_1 -= 1;
      this.currentConsumption1 -= 4;
    },
    plusm8310_1() {
      this.m8310_1 += 1;
      this.currentConsumption1 += 2;
    },
    minusm8310_1() {
      this.m8310_1 -= 1;
      this.currentConsumption1 -= 2;
    },
    plusm1391_1() {
      this.m1391_1 += 1;
      this.currentConsumption1 += 20;
    },
    minusm1391_1() {
      this.m1391_1 -= 1;
      this.currentConsumption1 += 20;
    },
    plusm8316_1() {
      this.m8316_1 += 1;
      this.currentConsumption1 += 8;
    },
    minusm8316_1() {
      this.m8316_1 -= 1;
      this.currentConsumption1 -= 8;
    },
    plusm8343_1() {
      this.m8343_1 += 1;
      this.currentConsumption1 += 4;
    },
    minusm8343_1() {
      this.m8343_1 -= 1;
      this.currentConsumption1 -= 4;
    },
    plusm8344_1() {
      this.m8344_1 += 1;
      this.currentConsumption1 += 8;
    },
    minusm8344_1() {
      this.m8344_1 -= 1;
      this.currentConsumption1 -= 8;
    },
    plusm8311_1() {
      this.m8311_1 += 1;
      this.currentConsumption1 += 4;
    },
    minusm8311_1() {
      this.m8311_1 -= 1;
      this.currentConsumption1 -= 4;
    },
    plusm8392_1() {
      this.m8392_1 += 1;
      this.currentConsumption1 += 20;
    },
    minusm8392_1() {
      this.m8392_1 -= 1;
      this.currentConsumption1 -= 20;
    },
    plusm8317_1() {
      this.m8317_1 += 1;
      this.currentConsumption1 += 16;
    },
    minusm8317_1() {
      this.m8317_1 -= 1;
      this.currentConsumption1 -= 16;
    },
    plusm1370_1() {
      this.m1370_1 += 1;
      this.currentConsumption1 += 70;
    },
    minusm1370_1() {
      this.m1370_1 -= 1;
      this.currentConsumption1 -= 70;
    },
    plusm1372_1() {
      this.m1372_1 += 1;
      this.currentConsumption1 += 125;
    },
    minusm1372_1() {
      this.m1372_1 -= 1;
      this.currentConsumption1 -= 125;
    },
    plusm1368_1() {
      this.m1368_1 += 1;
      this.currentConsumption1 += 85;
    },
    minusm1368_1() {
      this.m1368_1 -= 1;
      this.currentConsumption1 -= 85;
    },
    plusm1367_1() {
      this.m1367_1 += 1;
      this.currentConsumption1 += 110;
    },
    minusm1367_1() {
      this.m1367_1 -= 1;
      this.currentConsumption1 -= 110;
    },
    plusm1365_1() {
      this.m1365_1 += 1;
      this.currentConsumption1 += 125;
    },
    minusm1365_1() {
      this.m1365_1 -= 1;
      this.currentConsumption1 -= 125;
    },
    plusm1371_1() {
      this.m1371_1 += 1;
      this.currentConsumption1 += 40;
    },
    minusm1371_1() {
      this.m1371_1 -= 1;
      this.currentConsumption1 -= 40;
    },
    plusm8321_1() {
      this.m8321_1 += 1;
      this.currentConsumption1 += 70;
    },
    minusm8321_1() {
      this.m8321_1 -= 1;
      this.currentConsumption1 -= 70;
    },
    plusm1396_1() {
      this.m1396_1 += 1;
      this.currentConsumption1 += 125;
    },

    minusm1396_1() {
      this.m1396_1 -= 1;
      this.currentConsumption1 -= 125;
    },
    plusm1369_1() {
      this.m1369_1 += 1;
      this.currentConsumption1 += 110;
    },
    minusm1369_1() {
      this.m1369_1 -= 1;
      this.currentConsumption1 -= 110;
    },
    plusm1369_1() {
      this.m1369_1 += 1;
      this.currentConsumption1 += 110;
    },
    minusm1369_1() {
      this.m1369_1 -= 1;
      this.currentConsumption1 -= 110;
    },
    plusm13010_1() {
      this.m13010_1 += 1;
      this.currentConsumption1 += 4;
    },
    minusm13010_1() {
      this.m13010_1 -= 1;
      this.currentConsumption1 -= 4;
    },
    plusm1362_1() {
      this.m1362_1 += 1;
      this.currentConsumption1 += 4;
    },
    minusm1362_1() {
      this.m1362_1 -= 1;
      this.currentConsumption1 -= 4;
    },
    plusm1340_2() {
      this.m1340_2 += 1;
      this.currentConsumption2 += 2;
    },
    minusm1340_2() {
      this.m1340_2 -= 1;
      this.currentConsumption2 -= 2;
    },
    plusm1341_2() {
      this.m1341_2 += 1;
      this.currentConsumption2 += 4;
    },
    minusm1341_2() {
      this.m1341_2 -= 1;
      this.currentConsumption2 -= 4;
    },
    plusm8310_2() {
      this.m8310_2 += 1;
      this.currentConsumption2 += 2;
    },
    minusm8310_2() {
      this.m8310_2 -= 1;
      this.currentConsumption2 -= 2;
    },
    plusm1391_2() {
      this.m1391_2 += 1;
      this.currentConsumption2 += 20;
    },
    minusm1391_2() {
      this.m1391_2 -= 1;
      this.currentConsumption2 -= 20;
    },
    plusm8316_2() {
      this.m8316_2 += 1;
      this.currentConsumption2 += 8;
    },
    minusm8316_2() {
      this.m8316_2 -= 1;
      this.currentConsumption2 -= 8;
    },
    plusm8343_2() {
      this.m8343_2 += 1;
      this.currentConsumption2 += 4;
    },
    minusm8343_2() {
      this.m8343_2 -= 1;
      this.currentConsumption2 -= 4;
    },
    plusm8344_2() {
      this.m8344_2 += 1;
      this.currentConsumption2 += 8;
    },
    minusm8344_2() {
      this.m8344_2 -= 1;
      this.currentConsumption2 -= 8;
    },
    plusm8311_2() {
      this.m8311_2 += 1;
      this.currentConsumption2 += 4;
    },
    minusm8311_2() {
      this.m8311_2 -= 1;
      this.currentConsumption2 -= 4;
    },
    plusm8392_2() {
      this.m8392_2 += 1;
      this.currentConsumption2 += 20;
    },
    minusm8392_2() {
      this.m8392_2 -= 1;
      this.currentConsumption2 -= 20;
    },
    plusm8317_2() {
      this.m8317_2 += 1;
      this.currentConsumption2 += 16;
    },
    minusm8317_2() {
      this.m8317_2 -= 1;
      this.currentConsumption2 -= 16;
    },
    plusm1370_2() {
      this.m1370_2 += 1;
      this.currentConsumption2 += 50;
    },
    minusm1370_2() {
      this.m1370_2 -= 1;
      this.currentConsumption2 -= 50;
    },
    plusm1372_2() {
      this.m1372_2 += 1;
      this.currentConsumption2 += 100;
    },
    minusm1372_2() {
      this.m1372_2 -= 1;
      this.currentConsumption2 -= 100;
    },
    plusm1368_2() {
      this.m1368_2 += 1;
      this.currentConsumption2 += 50;
    },
    minusm1368_2() {
      this.m1368_2 -= 1;
      this.currentConsumption2 -= 50;
    },
    plusm1367_2() {
      this.m1367_2 += 1;
      this.currentConsumption2 += 100;
    },
    minusm1367_2() {
      this.m1367_2 -= 1;
      this.currentConsumption2 -= 100;
    },
    plusm1365_2() {
      this.m1365_2 += 1;
      this.currentConsumption2 += 100;
    },
    minusm1365_2() {
      this.m1365_2 -= 1;
      this.currentConsumption2 -= 100;
    },
    plusm1371_2() {
      this.m1371_2 += 1;
      this.currentConsumption2 += 25;
    },
    minusm1371_2() {
      this.m1371_2 -= 1;
      this.currentConsumption2 -= 25;
    },
    plusm8321_2() {
      this.m8321_2 += 1;
      this.currentConsumption2 += 25;
    },
    minusm8321_2() {
      this.m8321_2 -= 1;
      this.currentConsumption2 -= 25;
    },
    plusm1396_2() {
      this.m1396_2 += 1;
      this.currentConsumption2 += 50;
    },
    minusm1396_2() {
      this.m1396_2 -= 1;
      this.currentConsumption2 -= 50;
    },
    plusm1369_2() {
      this.m1369_2 += 1;
      this.currentConsumption2 += 100;
    },
    minusm1369_2() {
      this.m1369_2 -= 1;
      this.currentConsumption2 -= 100;
    },
    plusm13010_2() {
      this.m13010_2 += 1;
      this.currentConsumption2 += 4;
    },
    minusm13010_2() {
      this.m13010_2 -= 1;
      this.currentConsumption2 -= 4;
    },
    plusm1362_2() {
      this.m1362_2 += 1;
      this.currentConsumption2 += 4;
    },
    minusm1362_2() {
      this.m1362_2 -= 1;
      this.currentConsumption2 -= 4;
    },
    plusm1340_3() {
      this.m1340_3 += 1;
      this.currentConsumption3 += 5;
    },
    minusm1340_3() {
      this.m1340_3 -= 1;
      this.currentConsumption3 -= 5;
    },
    plusm1341_3() {
      this.m1341_3 += 1;
      this.currentConsumption3 += 10;
    },
    minusm1341_3() {
      this.m1341_3 -= 1;
      this.currentConsumption3 -= 10;
    },
    plusm8310_3() {
      this.m8310_3 += 1;
      this.currentConsumption3 += 5;
    },
    minusm8310_3() {
      this.m8310_3 -= 1;
      this.currentConsumption3 -= 5;
    },
    plusm1391_3() {
      this.m1391_3 += 1;
      this.currentConsumption3 += 50;
    },
    minusm1391_3() {
      this.m1391_3 -= 1;
      this.currentConsumption3 -= 50;
    },
    plusm8316_3() {
      this.m8316_3 += 1;
      this.currentConsumption3 += 20;
    },
    minusm8316_3() {
      this.m8316_3 -= 1;
      this.currentConsumption3 -= 20;
    },
    plusm1370_3() {
      this.m1370_3 += 1;
      this.currentConsumption3 += 70;
    },
    minusm1370_3() {
      this.m1370_3 -= 1;
      this.currentConsumption3 -= 70;
    },
    plusm1372_3() {
      this.m1372_3 += 1;
      this.currentConsumption3 += 100;
    },
    minusm1372_3() {
      this.m1372_3 -= 1;
      this.currentConsumption3 -= 100;
    },
    plusm1368_3() {
      this.m1368_3 += 1;
      this.currentConsumption3 += 65;
    },
    minusm1368_3() {
      this.m1368_3 -= 1;
      this.currentConsumption3 -= 65;
    },
    plusm1367_3() {
      this.m1367_3 += 1;
      this.currentConsumption3 += 80;
    },
    minusm1367_3() {
      this.m1367_3 -= 1;
      this.currentConsumption3 -= 80;
    },
    plusm1365_3() {
      this.m1365_3 += 1;
      this.currentConsumption3 += 100;
    },
    minusm1365_3() {
      this.m1365_3 -= 1;
      this.currentConsumption3 -= 100;
    },
    plusm1371_3() {
      this.m1371_3 += 1;
      this.currentConsumption3 += 40;
    },
    minusm1371_3() {
      this.m1371_3 -= 1;
      this.currentConsumption3 -= 40;
    },
    plusm8320_3() {
      this.m8320_3 += 1;
      this.currentConsumption3 += 70;
    },
    minusm8320_3() {
      this.m8320_3 -= 1;
      this.currentConsumption3 -= 70;
    },
    plusm1396_3() {
      this.m1396_3 += 1;
      this.currentConsumption3 += 60;
    },
    minusm1396_3() {
      this.m1396_3 -= 1;
      this.currentConsumption3 -= 60;
    },
    plusm1369_3() {
      this.m1369_3 += 1;
      this.currentConsumption3 += 80;
    },
    minusm1369_3() {
      this.m1369_3 -= 1;
      this.currentConsumption3 -= 80;
    },
    plusm8364_3() {
      this.m8364_3 += 1;
      this.currentConsumption3 += 1000;
    },
    minusm8364_3() {
      this.m8364_3 -= 1;
      this.currentConsumption3 -= 1000;
    },
    plusm13013_3() {
      this.m13013_3 += 1;
      this.currentConsumption3 += 10;
    },
    minusm13013_3() {
      this.m13013_3 -= 1;
      this.currentConsumption3 -= 10;
    },
  },
};
</script>
<style>
.all {
}

.withoutHeader {
}

.row {
  display: flex;
  flex-wrap: wrap;
}

.col {
  box-sizing: border-box;
}

.types {
  margin-top: 80px;
}

.background {
  background-color: #585857;
  justify-content: space-between;
  margin: 56px -15px;
  height: 170px;
  left: 0px;
  top: 200px;
  z-index: 99;
}

.logo {
  height: 40px;
  width: 200px;
  margin-left: 10px;
}

.head {
  width: 100%;
  top: 0;
  z-index: 100;
  background-color: #585857;
  width: 100%;
}

.connection {
  background-image: url("img/background-photo.jpg");
  background-size: cover; /* Растягивает изображение на всю область */
  background-position: center; /* Центрирует изображение */
  background-repeat: no-repeat; /* Запрет повторения изображения */
  height: 1000px;
  padding-top: 30px;
  padding-left: 12px;
}

.installimg1,
.installimg2,
.installimg3 {
  width: 297px;
  height: 155px;
}

.background2 {
  background-color: #585857;
  justify-content: space-between;
  margin: 0 -15px;
  height: 60px;
  left: 0px;
  top: 200px;
  margin-top: 10px;
}

.calc {
  color: #fff;
  margin-top: 16px;
  margin-left: 16px;
  font-size: 25px;
  font-weight: 600;
  padding-top: 10px;
}

.consumption1,
.consumption2,
.consumption3 {
  color: #fff;
  margin-top: 6px;
  margin-bottom: 5px;
  margin-left: 16px;
  margin-right: 10px;
  font-size: 22px;
  font-weight: 600;
  padding-right: 10px;
  padding: 0px 10px;
  background-color: #fff;
  color: #333;
  border-radius: 4px;
  border: 1px solid #585857;
  padding: 4px;
  padding-top: 14px;
  padding-bottom: 14px;
}

.chooseMasterInstall_1,
.chooseMasterInstall_2,
.chooseMasterInstall_3 {
  display: flex;
  justify-content: start;
  gap: 30px;
  margin-left: 0;
  margin-right: 0;
}

.chooseMaster {
}

.masterInstall {
  margin-top: 10px;
  justify-content: space-between;
  margin-left: 0;
  margin-right: 0;
}

.master_1000_1,
.master_1000_2,
.master_1000_3,
.master_2000_1,
.master_2000_2,
.master_2000_3,
.install_start_1,
.install_start_2,
.install_start_3,
.install_center_1,
.install_center_2,
.install_center_3 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px solid #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
}

.gray {
  background-color: #585857;
}

.chooseInstallType {
}

.btn {
  color: #585857;
  border-radius: 4px 0px 0px 4px;
  border: none;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 20px;
  line-height: 21px;
  height: 47px;
  width: 240px;
  margin-left: 18px;
}

.btn_center {
  color: #585857;
  border-radius: 0px;
  border: none;
  font-size: 20px;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  line-height: 21px;
  height: 47px;
  margin-left: 2px;
  width: 240px;
}

.btn_active {
  color: #fff;
  background-color: #00adbd;
  border-radius: 0px 4px 4px 0px;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 20px;
  line-height: 21px;
  height: 47px;
  border-width: 0px;
  margin-left: 1px;
  width: 240px;
}

.type {
  margin-left: 16px;
  margin-top: 10px;
}

#type {
  filter: drop-shadow(10px 10px 10px #464646);
}

.master {
  margin-left: 16px;
  margin-top: 25px;
}

.title {
  display: flex;
  justify-content: space-between;
  margin-top: 0;
  height: 80px;
  align-items: center;
}

.total {
  display: inline-block;
  max-width: 9%;
  border-left: 1px solid gray;
  padding-left: 8px;
}

.titles {
  margin-top: 40px;
  font-size: 25px;
  font-weight: 600;
}

.orangered {
  color: orangered;
}

.drips {
  margin: 0 auto;
}

.dripimg {
  width: 66px;
  height: 66px;
}

.btns {
  align-self: center;
  margin-left: 0px;
  vertical-align: center;
}

.drip {
  width: 356px;
  display: flex;
  align-items: center;
  gap: 5px;
}

h6 {
  margin-left: 10px;
  font-size: 14.5px;
  line-height: 16px;
  width: 170px;
  font-weight: 500;
}

.plus {
  align-self: center;
  margin-left: 5px;
  max-height: 25px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  width: 25px;
  font-size: 16px;
}

.minus {
  width: 25px;
  align-self: center;
  max-height: 25px;
  margin-left: 10px;
  margin-right: 5px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
}

.span {
  align-self: center;
  font-size: 20px;
}

.art {
  font-weight: 700;
}

.like {
  margin-top: 200px;
}

h5 {
  font-weight: 700;
  color: #585857;
  font-size: 22px;
  margin: 0px 0;
  margin-top: 0;
}

.header {
  color: #fff;
  font-weight: 750;
  font-size: 27.3px;
  margin-left: 12px;
  margin-top: 10px;
  height: 10px;
  margin-bottom: 5px;
}

.danger {
  color: orangered;
}

.totalcons {
  color: #00adbd;
}

.question {
  padding-top: 10px;
  height: 17px;
  width: 17px;
}

.cons {
  padding: 8px;
}

.hide {
  display: none;
}

.center {
  width: 140px;
  margin-left: 100px;
  border-radius: 4px;
}

.prechoose {
}

.choose {
  display: flex;
  justify-content: start;
  gap: 30px;
  margin-left: 3px;
}

.install {
  width: 326px;
  font-weight: 500;
  border: 2px solid #00adbd;
  border-radius: 6px;
  text-align: center;
  text-decoration-color: #585857;
  background-color: white;
}

.install:hover {
  opacity: 94%;
}

.install_title {
  /* color: #00adbd; */
  text-decoration: none;
  color: inherit;
}

.install_text {
  margin-top: 10px;
  font-size: 14px;
  padding-left: 2px;
  padding-right: 2px;
  text-decoration: none;
}

.bg-white {
  background-color: white;
}

.micro_drip_calculator {
  margin: 0;
  padding: 0;
  color: white;
  text-shadow: -1px -1px 0 black, 1px -1px 0 black, -1px 1px 0 black,
    1px 1px 0 black;
  font-size: 48px;
}

.micro_drip_calculator1,
.micro_drip_calculator2,
.micro_drip_calculator3 {
  font-size: 26px;
  padding-left: 4px;
}

.works {
  text-decoration: underline;
}

.choose_your_type {
  color: white;
  text-shadow: -1px -1px 0 black, 1px -1px 0 black, -1px 1px 0 black,
    1px 1px 0 black;
  margin-top: 160px;
  font-size: 36px;
}

.px80 {
}

.master_1000_1:hover,
.master_2000_1:hover,
.install_start_1:hover,
.install_center_1:hover,
.master_1000_2:hover,
.master_2000_2:hover,
.install_start_2:hover,
.install_center_2:hover,
.master_1000_3:hover,
.master_2000_3:hover,
.install_start_3:hover,
.install_center_3:hover {
  opacity: 0.8;
  cursor: pointer;
}

.teal {
  background-color: #00adbd;
}

@media screen and (max-width: 560px) {
  .consumption1,
  .consumption2,
  .consumption3 {
    font-size: 16px;
  }
  .micro_drip_calculator {
    font-size: 34px;
  }
}

@media screen and (max-width: 397px) {
  .logo {
    width: 100px;
    height: 20px;
  }
  .consumption1,
  .consumption2,
  .consumption3 {
    font-size: 12px;
  }
}
</style>
<!-- <style>
.row {
  display: flex;
  flex-wrap: wrap;
  margin: 0 -25px;
}

.col {
  box-sizing: border-box;
}

.types {
  margin-top: 80px;
}

.background {
  background-color: #585857;
  justify-content: space-between;
  margin: 56px -15px;
  height: 170px;
  left: 0px;
  top: 200px;
  z-index: 99;
}

.logo {
  height: 70px;
  width: 200px;
}

.head {
  position: fixed;
  width: 1190px;
  top: 0;
  z-index: 100;
}

.installimg1 {
  width: 297px;
  height: 155px;
}

.installimg2 {
  width: 297px;
  height: 155px;
}

.installimg3 {
  width: 297px;
  height: 155px;
}

.background2 {
  background-color: #585857;
  justify-content: space-between;
  margin: 0 -15px;
  height: 60px;
  left: 0px;
  top: 200px;
  margin-top: 10px;
}

.calc {
  color: #fff;
  margin-top: 16px;
  margin-left: 16px;
  font-size: 25px;
  font-weight: 600;
  padding-top: 10px;
}

.consumption1,
.consumption2,
.consumption3 {
  color: #fff;
  margin-top: 6px;
  margin-bottom: 5px;
  margin-left: 16px;
  margin-right: 10px;
  font-size: 22px;
  font-weight: 600;
  padding-right: 10px;
  padding: 0px 10px;
  background-color: #fff;
  color: #333;
  /* background-color: #bd4c00; */
  border-radius: 4px 4px 4px 4px;
}

.chooseMasterInstall_1 {
  margin-left: 0;
  margin-right: 0;
}

.chooseMaster {
  border: 1px solid #e6e7e8;
  border-radius: 7px;
  height: 70px;
  width: 550px;
}

.masterInstall {
  margin-top: 10px;
  justify-content: space-between;
  margin-left: 0;
  margin-right: 0;
}

.master_1000_1 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-left: 10px;
}

.gray {
  background-color: #585857;
}

.master_2000_1 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}

.chooseInstallType {
  border: 1px solid #e6e7e8;
  border-radius: 7px;
  height: 70px;
  width: 550px;
  margin-left: 20px;
}

.install_start_1 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-left: 10px;
  text-decoration: none;
}

.install_center_1 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}

.chooseMasterInstall_2 {
  margin-left: 0;
  margin-right: 0;
}

.chooseMaster {
  border: 1px solid #e6e7e8;
  border-radius: 7px;
  height: 70px;
  width: 550px;
}

.masterInstall {
  margin-top: 10px;
  justify-content: space-between;
  margin-left: 0;
  margin-right: 0;
}

.master_1000_2 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-left: 10px;
}

.master_2000_2 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}

.chooseInstallType {
  border: 1px solid #e6e7e8;
  border-radius: 7px;
  height: 70px;
  width: 550px;
  margin-left: 20px;
}

.install_start_2 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-left: 10px;
}

.install_center_2 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}

.chooseMasterInstall_3 {
  margin-left: 0;
  margin-right: 0;
}

.chooseMaster {
  border: 1px solid #e6e7e8;
  border-radius: 7px;
  height: 70px;
  width: 550px;
}

.masterInstall {
  margin-top: 10px;
  justify-content: space-between;
  margin-left: 0;
  margin-right: 0;
}

.master_1000_3 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-left: 10px;
}

.master_2000_3 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}

.chooseInstallType {
  border: 1px solid #e6e7e8;
  border-radius: 7px;
  height: 70px;
  width: 550px;
  margin-left: 20px;
}

.install_start_3 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-left: 10px;
}

.install_center_3 {
  width: 255px;
  color: #fff;
  background-color: #585857;
  border: 1px soild #585857;
  border-radius: 3px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}

.btn {
  color: #585857;
  border-radius: 4px 0px 0px 4px;
  border: none;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 20px;
  line-height: 21px;
  height: 47px;
  width: 240px;
  margin-left: 18px;
}

.btn_center {
  color: #585857;
  border-radius: 0px;
  border: none;
  font-size: 20px;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  line-height: 21px;
  height: 47px;
  margin-left: 2px;
  width: 240px;
}

.btn_active {
  color: #fff;
  background-color: #00adbd;
  border-radius: 0px 4px 4px 0px;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 20px;
  line-height: 21px;
  height: 47px;
  border-width: 0px;
  margin-left: 1px;
  width: 240px;
  /*filter: drop-shadow(6px 10px 10px #464646);*/
}

.type {
  margin-left: 16px;
  margin-top: 10px;
}

#type {
  filter: drop-shadow(10px 10px 10px #464646);
}

.master {
  margin-left: 16px;
  margin-top: 25px;
}

.title {
  display: flex;
  justify-content: space-between;
  margin-top: 0;
  height: 80px;
}

.total {
  display: inline-block;
  max-width: 9%;
  border-left: 1px solid gray;
  padding-left: 8px;
}

.titles {
  margin-top: 40px;
  font-size: 25px;
  font-weight: 600;
}

.orangered {
  color: orangered;
}

.drips {
  margin: 0 auto;
}

.dripimg {
  width: 66px;
  height: 66px;
}

.btns {
  align-self: center;
  margin-left: 0px;
  vertical-align: center;
}

.drip {
  margin-right: 30px;
  margin-top: 24px;
  width: 356px;
  display: flex;
}

h6 {
  margin-left: 10px;
  font-size: 14.5px;
  line-height: 16px;
  width: 170px;
  font-weight: 500;
}

.plus {
  align-self: center;
  margin-left: 5px;
  max-height: 25px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  width: 25px;
  font-size: 16px;
}

.minus {
  width: 25px;
  align-self: center;
  max-height: 25px;
  margin-left: 10px;
  margin-right: 5px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
}

.span {
  align-self: center;
  font-size: 20px;
}

.art {
  font-weight: 700;
}

.like {
  margin-top: 200px;
}

h5 {
  font-weight: 700;
  color: #585857;
  font-size: 22px;
  margin: 0px 0;
  margin-top: 0;
}

.header {
  color: #fff;
  /*text-transform: uppercase;*/
  font-weight: 750;
  font-size: 27.3px;
  margin-left: 12px;
  margin-top: 10px;
  height: 10px;
  margin-bottom: 5px;
}

.danger {
  color: orangered;
}

.totalcons {
  color: #00adbd;
}

.question {
  padding-top: 10px;
  height: 17px;
  width: 17px;
}

.cons {
  padding: 8px;
}

.hide {
  display: none;
}

.center {
  width: 140px;
  margin-left: 100px;
  border-radius: 4px 4px 4px 4px;
}

.prechoose {
  margin-top: 80px;
}

.choose {
  margin-top: 0px;
  padding-top: 10px;
  padding-left: 10px;
  max-height: 650px;
  max-width: 1170px;
  border: 2px solid #e6e7e8;
  border-radius: 17px 17px 17px 17px;
  margin: 0;
  justify-content: space-around;
  color: #585857;
  font-weight: 600;
}

.install {
  width: 300px;
  font-weight: 500;
  border: 2px solid #00adbd;
  border-radius: 6px;
  text-align: center;
}

.install_title {
  color: #00adbd;
}

.install_text {
  margin-top: 10px;
  font-size: 14px;
}

.micro_drip_calculator1,
.micro_drip_calculator2,
.micro_drip_calculator3 {
  font-size: 26px;
  padding-top: 10px;
}

.works {
  text-decoration: underline;
}

.choose_your_type {
  padding-top: 30px;
}

.px80 {
  padding-top: 80px;
}

.master_1000_1:hover,
.master_2000_1:hover,
.install_start_1:hover,
.install_center_1:hover,
.master_1000_2:hover,
.master_2000_2:hover,
.install_start_2:hover,
.install_center_2:hover,
.master_1000_3:hover,
.master_2000_3:hover,
.install_start_3:hover,
.install_center_3:hover {
  opacity: 0.8;
  cursor: pointer;
}

.teal {
  background-color: #00adbd;
}
</style> -->
