<script lang="ts">
  import {
    CastIcon,
    HardDriveIcon,
    ImageIcon,
    LockIcon,
    RefreshCwIcon,
    Share2Icon,
  } from "svelte-feather-icons";

  import logotypeDark from "$lib/assets/logotype-dark.svg";
  import landingGraphic from "$lib/assets/landing-graphic.svg";
  import landingBackground from "$lib/assets/landing-background.svg";
  import TeaserImage from "$lib/ui/TeaserImage.svelte";

  let installationEl: HTMLDivElement;

  const installs = [
    {
      title: "macOS / Linux",
      steps: `curl -sSf https://sshx.io/get | sh`,
    },
    {
      title: "Rust (from source)",
      steps: `cargo install sshx`,
    },
  ];

  const socials = [
    {
      title: "🤖\xa0 GitHub",
      href: "https://github.com/ekzhang/sshx",
    },
    {
      title: "🌸\xa0 Twitter",
      href: "https://twitter.com/ekzhang1",
    },
    {
      title: "💌\xa0 Email",
      href: "mailto:ekzhang1@gmail.com",
    },
    {
      title: "🌎\xa0 Website",
      href: "https://www.ekzhang.com",
    },
  ];

  let selectedInstall = installs[0];

  function scrollToInstallation() {
    installationEl.scrollIntoView({ behavior: "smooth" });
  }
</script>

<div class="overflow-x-hidden absolute inset-0">
  <main class="max-w-screen-xl mx-auto px-4 md:px-8 lg:px-16">
    <header class="my-12">
      <img class="h-16 -mx-1" src={logotypeDark} alt="sshx logo" />
    </header>
    <h1>
      一个基于网络安全的
      <span class="title-gradient">协同</span> 终端
    </h1>
    <h3>
      <code>
        请注意,当前为<a target="_blank"
            rel="noreferrer"
            class="underline underline-offset-2 text-gray-300"
            href="https://tools.0x5c0f.cc/">博主</a>自建节点,与官方差异仅首页翻译。来访者可任意使用，但请优先以<a target="_blank"
            rel="noreferrer"
            class="underline underline-offset-2 text-gray-300"
            href="https://sshx.io/">官方</a>为准🙏🙏🙏。</code></h3>

    <div class="relative">
      <div
        class="absolute scale-150 md:scale-100 md:left-[180px] md:top-[-200px] md:w-[1000px] -z-10"
      >
        <img class="select-none" src={landingBackground} alt="" />
      </div>
      <div class="md:absolute md:left-[500px] md:w-[1000px]">
        <img
          class="mt-5 mb-8 w-[720px]"
          width={813}
          height={623}
          src={landingGraphic}
          alt="two terminal windows running sshx and three live cursors"
        />
      </div>
    </div>

    <section class="my-12 space-y-6 text-lg md:max-w-[460px] text-zinc-400">
      <p>
        <code>sshx</code> 允许您通过链接与任何人共享终端, 并且支持<b>多人协作、无限终端</b>
      </p>
      <p>
        它具有<b>实时协作</b>, 包括远程光标和聊天。它的<b>速度很快</b>并且是<b>端到端的加密</b>。
        是使用Rust编写的轻量服务。
      </p>
      <p>
        使用一个命令安装 <code>sshx</code>， 可用于教学、调试、或者是云访问。
      </p>
    </section>

    <div class="pb-12 md:pb-36">
      <button
        class="bg-pink-700 hover:bg-pink-600 active:ring-4 active:ring-pink-500/50 text-lg font-medium px-8 py-2 rounded-full"
        on:click={scrollToInstallation}
      >
        Get Started
      </button>
    </div>

    <div
      class="mt-8 md:mt-32 grid md:grid-cols-2 xl:grid-cols-3 gap-4 md:gap-6"
    >
      <div class="feature-block">
        <div class="feature-icon">
          <CastIcon size="14" />
        </div>
        <h3>协同</h3>
        <p>通过共享的独特安全浏览器链接邀请他人。</p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <HardDriveIcon size="14" />
        </div>
        <h3>跨平台</h3>
        <p>在macOS和Linux上，只需一秒钟即可安装客户端。</p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <ImageIcon size="14" />
        </div>
        <h3>无限终端</h3>
        <p>
          可以创建多个终端，并且任意排列它。
        </p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <RefreshCwIcon size="14" />
        </div>
        <h3>协作状态</h3>
        <p>在操作时，你可以实时查看其他人的姓名和光标</p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <LockIcon size="14" />
        </div>
        <h3>端到端加密</h3>
        <p>
          安全地发送终端数据;服务器永远不会看到您键入的内容。
        </p>
      </div>
      <div class="feature-block">
        <div class="feature-icon">
          <Share2Icon size="14" />
        </div>
        <h3>超快的mesh网络</h3>
        <p>
          从任何地方连接到全球网络中最近的分布式节点
        </p>
      </div>
    </div>

    <div class="my-48 hidden md:block">
      <TeaserImage />
    </div>

    <h2 bind:this={installationEl} class="mt-40 mb-16">
      通过<span class="title-gradient">两步</span>快速安装
    </h2>

    <div
      class="mx-auto max-w-screen-lg grid lg:grid-cols-2 gap-16 lg:text-center mb-12 text-lg text-zinc-300"
    >
      <div class="space-y-6">
        <h3 class="step-heading">
          <span class="pill mr-3">1</span> 安装 <b>CLI</b>
        </h3>
        <p class="text-zinc-400">
          通过终以下终端命令获取<code>sshx</code>CLI
        </p>
        <div class="flex flex-col items-start text-base">
          <div class="flex rounded-t text-sm bg-zinc-900">
            {#each installs as method}
              <button
                class="px-2 py-1 border-l border-t last:border-r border-zinc-500 first:rounded-tl last:rounded-tr"
                class:bg-zinc-700={selectedInstall === method}
                on:click={() => (selectedInstall = method)}
              >
                {method.title}
              </button>
            {/each}
          </div>
          <pre class="rounded-b rounded-r w-full">{selectedInstall.steps}</pre>
        </div>

        <p class="text-zinc-400">
          如果你愿意，你也可以从 <a
            target="_blank"
            rel="noreferrer"
            class="underline underline-offset-2 text-zinc-300"
            href="https://github.com/ekzhang/sshx">源代码</a
          > 构建它。
        </p>
      </div>
      <div class="space-y-6">
        <h3 class="step-heading">
          <span class="pill mr-3">2</span> 共享你的终端
        </h3>

        <p class="text-zinc-400">直接运行即可</p>

        <pre class="rounded">sshx</pre>

        <p class="text-zinc-400">
          这将启动一个实时的加密会话，在您的浏览器中打开链接即可加入。
        </p>
      </div>
    </div>

    <hr class="mt-40 mb-12" />

    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-4 md:gap-6 mb-6">
      {#each socials as social}
        <a
          target="_blank"
          rel="noreferrer"
          href={social.href}
          class="border border-zinc-700 hover:bg-zinc-900 transition-colors p-4 text-center text-lg font-medium rounded-lg"
        >
          {social.title}
        </a>
      {/each}
    </div>

    <p class="mb-12 text-center text-zinc-400">
      open source, &copy; Eric Zhang 2023
    </p>
  </main>
  <footer class="text-center text-zinc-400" id='beian'>
      <span>
				<a href="https://beian.mps.gov.cn/#/query/webSearch?code=50010602503871" rel="noreferrer" target="_blank">
					<img src="https://tools.0x5c0f.cc/img/gov.png" style="width: 21px; display: inline-block;vertical-align: middle;margin-right: 1px;"/>   
					渝公网安备 50010602503871
				</a>
			</span>
			<span>
				<a href="http://beian.miit.gov.cn" target="_blank">渝ICP备2020011834号-2</a>
			</span>
		</footer>
</div>

<style lang="postcss">
  h1 {
    @apply font-medium text-4xl sm:text-5xl max-w-[26ch] py-2 sm:tracking-tight;
    line-height: 1.15;
  }

  h2 {
    @apply font-medium text-3xl sm:text-4xl md:text-center scroll-mt-16;
  }

  b {
    @apply text-zinc-300 font-medium;
  }

  code {
    @apply text-[0.9em] text-zinc-200 font-medium bg-zinc-700 px-1 py-0.5 rounded;
  }

  pre {
    @apply bg-zinc-900 p-3 whitespace-pre-wrap border border-zinc-500;
  }

  hr {
    @apply mx-auto md:w-1/2 border-zinc-800;
  }

  .title-gradient {
    @apply text-transparent bg-clip-text bg-gradient-to-r from-fuchsia-400 to-blue-500;
  }

  .feature-block {
    @apply relative border rounded-lg border-transparent p-6 sm:p-8;
    background: #111111 padding-box;
  }

  .feature-block::before {
    content: "";
    @apply absolute inset-0;
    z-index: -1;
    margin: -1px;
    border-radius: inherit;
    background: linear-gradient(
      160deg,
      rgba(255, 255, 255, 0.36) 5%,
      rgba(255, 255, 255, 0.08) 25%,
      rgba(255, 255, 255, 0.24) 50%,
      rgba(255, 255, 255, 0.08) 75%,
      rgba(255, 255, 255, 0.28) 95%
    );
    opacity: 0.5;
    transition: opacity 200ms;
  }

  .feature-block:hover::before {
    opacity: 1;
  }

  .feature-block h3 {
    @apply font-medium mb-2;
  }

  .feature-block p {
    @apply text-zinc-400;
  }

  .feature-icon {
    @apply inline-block p-3 rounded-full mb-3 shadow-md border border-zinc-600;
  }

  .step-heading {
    @apply text-2xl text-zinc-200 font-medium flex items-center md:justify-center;
  }

  .pill {
    @apply flex justify-center items-center w-7 h-7 rounded-full;
    @apply text-base font-normal border border-current;
  }
</style>
