<script lang="ts">
    import "../app.css";

    const words: string[][] = [
        ["borrow", "[ˈbɒrəʊ]", "занимать"],
        ["lend", "[lend]", "одолживать"],
        ["purpose", "[ˈpɜːrpəs]", "предназначение"],
        ["proposal", "[prəˈpəʊzl]", "предложение"],
        ["entertainment", "[ˌentəˈteɪnmənt]", "развлечение"],
        ["obtain", "[əbˈteɪn]", "получать"],
        ["share", "[ʃeər]", "делиться"],
        ["environmentally", "[ɪnˌvaɪrənˈmentəli]", "экологически"],
        ["perhaps", "[pəˈhæps]", "возможно"],
        ["delicious", "[dɪˈlɪʃəs]", "вкусный"],
        [
            "system maintenance",
            "[ˈsɪstəm ˈmeɪntənəns]",
            "системное обслуживание",
        ],
        ["expansion card", "[ɪkˈspænʃn kɑːrd]", "плата расширения"],
        ["encryption", "[ɪnˈkrɪpʃn]", "шифрование"],
        //
        //
        ["to burn image", "[tuː bɜːrn ˈɪmɪdʒ]", "записывать изображение"],
        ["dubbing", "[ˈdʌbɪŋ]", "копирование"],
        ["mark-up language", "[mɑːrk ʌp ˈlæŋɡwɪdʒ]", "язык разметки"],
        ["analyst", "[ˈænəlɪst]", "аналитик"],
        ["advertisement", "[ˌædvərˈtaɪzmənt]", "реклама"],
        ["annoying sidelight", "[əˈnɔɪɪŋ ˈsaɪlaɪt]", "информационный шум"],
        ["signature", "[ˈsɪɡnətʃər]", "подпись"],
        ["to admit", "[tuː ədˈmɪt]", "признавать"],
        ["admitted", "[ədˈmɪtɪd]", "допущенный"],
        ["to stand it", "[tuː stænd ɪt]", "выдерживать"],
        ["to be made of", "[tuː biː meɪd ʌv]", "сделан из чего-то"],
        [
            "recycling of garbage",
            "[ˌriːˈsaɪklɪŋ ʌv ˈɡɑːrbɪdʒ]",
            "переработка мусора",
        ],
        ["useful", "[ˈjuːsfəl]", "полезный"],
        ["harmful", "[ˈhɑːrmfəl]", "вредный"],
        ["waste", "[weɪst]", "отходы"],
        ["rubbish", "[ˈrʌbɪʃ]", "мусор"],
        ["identical", "[aɪˈdentɪkl]", "один к одному (такой же)"],
        ["personality", "[ˌpɜːrsəˈnæləti]", "личность"],
        ["aged", "[eɪdʒd]", "старый (в возрасте)"],
        ["clothes", "[kloʊðz]", "одежда"],
        //
        //
        ["consist of", "[kənˈsɪst ʌv]", "состоять из чего-то"],
        ["speech babbles", "[spiːtʃ ˈbæblz]", "область диалога"],
        ["acquaintance", "[əˈkweɪntəns]", "знакомый"],
        ["sparkle", "[ˈspɑːrkl]", "искриться"],
        ["sparkling", "[ˈspɑːrk.lɪŋ]", "сияние (блеск)"],
        ["sense", "[sens]", "восприятие"],
        ["suspect", "[səˈspɛkt]", "подозревать (подозреваемый)"],
        ["loathe", "[loʊð]", "испытывать"],
        ["desire", "[dɪˈzaɪər]", "желать"],
        ["appreciate", "[əˈpriːʃieɪt]", "ценить"],
        ["taste", "[teɪst]", "отведать"],
        ["possess", "[pəˈzes]", "владеть"],
        [
            "you need to know when to stop",
            "[juː niːd tuː noʊ wɛn tuː stɒp]",
            "нужно знать, когда остановиться",
        ],
        ["depend on", "[dɪˈpɛnd ɒn]", "зависеть"],
        ["offsite", "[ˈɒfsaɪt]", "внешний"],
        ["loss (data)", "[lɒs]", "потеря"],
        ["volumes (of data)", "[ˈvɒljuːmz]", "диск (том, объем)"],
        ["theft", "[θɛft]", "воровство"],
        ["emerging (method)", "[ɪˈmɜːrdʒɪŋ]", "появляющийся метод"],
        ["emerge", "[ɪˈmɜːrdʒ]", "появляться"],
        ["cloud computing", "[klaʊd ˈkɒmpjʊtɪŋ]", "облачные вычисления"],
        ["allow", "[əˈlaʊ]", "разрешить"],
        ["colleagues", "[ˈkɒliːɡz]", "коллеги"],
        ["eliminates", "[ɪˈlɪmɪneɪts]", "устранять (уничтожать)"],
        ["flood", "[flʌd]", "наводнение"],
        ["reliable", "[rɪˈlaɪəbl]", "благонадежный"],
        ["disaster", "[dɪˈzɑːstər]", "бедствие (несчастье)"],
        ["flawless operation", "[ˈflɔːləs ˌɒpəˈreɪʃn]", "безотказная работа"],
        ["interfere", "[ˌɪntəˈfɪər]", "вмешиваться"],
        ["go viral", "[ɡoʊ ˈvaɪrəl]", "приобрести вирусную популярность"],
        ["deliver the goods", "[dɪˈlɪvər ðə ɡʊdz]", "добиться результатов"],
        ["advantage", "[ədˈvæntɪdʒ]", "преимущество"],
        ["benefit", "[ˈbɛnɪfɪt]", "польза (благо)"],
        ["drawback", "[ˈdrɔːbæk]", "недостаток"],
        ["retrieve", "[rɪˈtriːv]", "восстановление"],
        ["recruitment", "[rɪˈkruːtmənt]", "набор (наем)"],
        //
        //
        ["specification", "[ˌspɛsɪfɪˈkeɪʃn]", "тех. поддержка"],
        ["loan", "[loʊn]", "ссуда"],
        ["customer", "[ˈkʌstəmər]", "потребитель"],
        ["satisfaction", "[ˌsætɪsˈfækʃn]", "удовлетворение"],
        ["survey", "[sɜːrˈveɪ]", "опрос"],
        ["promotion", "[prəˈmoʊʃn]", "продвижение"],
        ["stock (management)", "[stɒk]", "управление товарами"],
        ["quantity", "[ˈkwɒntəti]", "кол-во"],
        ["report", "[rɪˈpɔːrt]", "отчет"],
        ["purchasing needs", "[ˈpɜːrtʃəsɪŋ niːdz]", "снабжение"],
        ["convenience", "[kənˈviːniəns]", "удобство"],
        ["pet peeve", "[pɛt pɪv]", "раздражающая привычка"],
    ];

    const usedWords: string[][] = [];

    let wordIndex: number | null = null;
    let choise: string[] = getRandomWords();
    let isStarting: boolean = false;
    let result: string = "";
    let showBlockWithResult: boolean = false;
    let wordsLength = words.length;
    let usedWordsLength = usedWords.length;

    function start() {
        if (!isStarting) {
            isStarting = true;
        }
        clearAll();
        choise = getRandomWords();
    }

    function getRandomWords() {
        wordIndex = Math.floor(Math.random() * (words.length + 1));
        return words[wordIndex];
    }

    function check() {
        showBlockWithResult = true;
    }

    function continueTrain() {
        showBlockWithResult = false;
        updateArrayWithWords();
        start();
    }

    function updateArrayWithWords() {
        if (wordIndex) {
            usedWords.push(choise);
            words.splice(wordIndex, 1);

            wordsLength = words.length;
            usedWordsLength = usedWords.length;
        } else if (wordIndex === 0) {
            alert("Слова закончились");
        } else {
            alert("You have problems in the code.");
        }
    }

    function clearAll() {
        result = "";
    }
</script>

<section
    class="flex flex-col gap-y-5 justify-center items-center w-full dark:bg-gray-800 h-screen"
>
    <section class="-mt-52">
        <section
            class="flex flex-col min-w-0 text-white sm:min-w-[550px] gap-y-3 mb-4"
        >
            <div>Всего: {wordsLength}</div>
            <div>Пройдено: {usedWordsLength}</div>
        </section>
        <section
            class="flex border-2 shadow-2xl rounded-2xl justify-center items-center p-5 min-h-[200px] min-w-0 sm:min-w-[550px] mx-2 bg-white dark:bg-gray-800"
        >
            {#if words.length !== 0}
                <div class="block m-auto w-full">
                    <div
                        class="block w-full text-center text-2xl text-black dark:text-white"
                    >
                        <p>{choise[2]}</p>
                    </div>

                    <div
                        class="block w-full text-center text-2xl text-black dark:text-white"
                    >
                        <p>{choise[1]}</p>
                    </div>

                    <div class="mt-4">
                        <div>
                            <input
                                type="text"
                                class="input border-2 border-gray-200 dark:border-gray-600 w-full p-3 rounded-lg bg-white dark:bg-gray-700 text-black dark:text-white"
                                placeholder="Word"
                                bind:value={result}
                            />
                        </div>
                    </div>

                    {#if showBlockWithResult}
                        <div class="mt-4">
                            <div>
                                <p class="text-green-500">{choise[0]}</p>
                            </div>
                        </div>

                        {#if result !== choise[0]}
                            <div class="mt-4">
                                <div>
                                    <p class="text-red-500">
                                        {#if result === ""}
                                            {choise[0]}
                                        {:else}
                                            {result}
                                        {/if}
                                    </p>
                                </div>
                            </div>
                        {/if}
                    {/if}

                    <div class="block w-full mt-4">
                        <button
                            on:click={() =>
                                showBlockWithResult ? continueTrain() : check()}
                            class="btn flex m-auto rounded-2xl border-2 py-3 px-8 border-gray-200 dark:border-gray-600 bg-white dark:bg-gray-700 text-black dark:text-white"
                        >
                            {#if showBlockWithResult}
                                Continue
                            {:else}
                                Check
                            {/if}
                        </button>
                    </div>
                </div>
            {/if}
        </section>
    </section>
</section>
