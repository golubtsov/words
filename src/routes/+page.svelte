<script lang="ts">
    import "../app.css";

    const words = [
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
    ];

    let choise: string[] = getRandomWords();
    let isStarting: boolean = false;
    let result: string = "";

    function start() {
        if (!isStarting) {
            isStarting = true;
        }
        clearAll();
        choise = getRandomWords();
    }

    function getRandomWords() {
        let n = Math.floor(Math.random() * (words.length + 1));
        return words[n];
    }

    function check() {
        if (result === choise[0]) {
            alert("Good!");
        } else {
            alert(
                `You have the error\n Right - ${choise[0]}\n Wrong - ${result}`,
            );
        }
        start();
    }

    function clearAll() {
        result = "";
    }
</script>

<section class="flex flex-1 my-36 justify-center items-center w-full">
    <section
        class="flex border-2 shadow-2xl rounded-2xl justify-center items-center p-5 min-h-[200px] min-w-[550px] mx-5"
    >
        {#if words.length === 0 && !isStarting}
            <div class="flex w-full m-auto p-2">
                <button
                    class="flex m-auto py-1 border-2 text-2xl rounded-2xl px-4"
                    on:click={() => start()}
                >
                    words
                </button>
            </div>
        {/if}

        {#if words.length !== 0}
            <div class="block m-auto w-full">
                <div class="block w-full text-center text-2xl">
                    <p>{choise[2]}</p>
                </div>

                <div class="block w-full text-center text-2xl">
                    <p>{choise[1]}</p>
                </div>

                <div class="mt-4">
                    <div>
                        <input
                            autofocus
                            type="text"
                            class="input border-2 border-gray-200 w-full p-3 rounded-lg"
                            placeholder="Word"
                            bind:value={result}
                        />
                    </div>
                </div>

                <div class="block w-full mt-4">
                    <button
                        on:click={check}
                        class="btn flex m-auto rounded-2xl border-2 py-3 px-8 border-gray-200"
                    >
                        Check
                    </button>
                </div>
            </div>
        {/if}
    </section>
</section>
