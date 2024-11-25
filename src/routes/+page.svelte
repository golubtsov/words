<script lang="ts">
    const words = [
        ["important", "[ɪmˈpɔːrtnt]", "важный"],
        ["giver", "[ˈɡaɪvər]", "даритель"],
        ["virtual", "[ˈvɜːrtʃuəl]", "виртуальный"],
        ["visit", "[ˈvɪzɪt]", "посещение"],
        ["tint", "[tɪnt]", "оттенок"],
        ["burglion", "[ˈbɜːrɡliən]", "кража со взломом"],
        ["shoplifter", "[ˈʃɒpˌlɪftər]", "вор в магазине"],
        ["knauf", "[nɔːf]", "кнауф (марка)"],
        ["exhausted", "[ɪɡˈzɔːstɪd]", "истощенный"],
        ["discover", "[dɪˈskʌvər]", "открывать"],
        ["proposal", "[prəˈpəʊzəl]", "предложение (проект)"],
        ["soldown", "[ˈsəʊldaʊn]", "продажа"],
        ["accomplish", "[əˈkɒmplɪʃ]", "достигать"],
        ["go into", "[ɡəʊ ˈɪntə]", "входить в"],
        ["harness", "[ˈhɑːrnɪs]", "упряжь"],
        ["vile", "[vaɪl]", "подлый"],
        ["dull", "[dʌl]", "скучный"],
    ];

    let choise: string[] = [];
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
        if (result !== "") {
            if (result === choise[0]) {
                alert("Good!");
            } else {
                alert(
                    `You have the error\n Wrong - ${choise[0]}\n Right - ${result}`,
                );
            }
        }
        start();
    }

    function clearAll() {
        // choise = [];
        result = "";
        // v3 = "";
        // v2Error = false;
        // v3Error = false;
    }
</script>

<section
    class="flex flex-1 mt-36 absolute border-2 shadow-2xl rounded-2xl w-full p-5 min-h-[200px]"
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
                        type="text"
                        class="input"
                        placeholder="Word"
                        bind:value={result}
                    />
                </div>
            </div>

            <div class="block w-full mt-4">
                <button on:click={check} class="btn rounded-2xl">
                    Check
                </button>
            </div>
        </div>
    {/if}
</section>
