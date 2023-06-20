<script setup lang='ts'>
import { computed } from 'vue'
import { NCard, NModal } from 'naive-ui'

const props = defineProps<Props>()

const emit = defineEmits<Emit>()

interface Props {
  visible: boolean
}

interface Emit {
  (e: 'update:visible', visible: boolean): void
}

const show = computed({
  get() {
    return props.visible
  },
  set(visible: boolean) {
    emit('update:visible', visible)
  },
})
</script>

<template>
  <NModal v-model:show="show" :auto-focus="false">
    <NCard role="dialog" aria-modal="true" :bordered="false" preset="dialog" title="感谢支持！！" style="width: 95%; max-width: 50%;height: 95%; max-height: 645px" close-on-esc>
      <div class="flex items-center flex-col justify-center mt-4 text-center ">
        <div>永久免费提供学习和测试，支持上下文，支持开启关闭联网模式，支持保存会话，切勿发布至国内平台或微信分享</div>
        <div />
        <div>禁止发布、传播任何违法、违规内容，使用本网站，视您接受并同意<a target="_blank" style="color:#006eff;" href="https://docs.qq.com/doc/DVFdaY1lvWHFSWU5w">《免责声明》</a></div>
        <b style="color:red;">每人每月捐个三元、服务就能永久免费下去！！⬇️⬇️⬇️可定期自愿捐赠投喂，不捐也能随便用</b>
        <div>服务器昂贵,接口昂贵,但网站免费！！如果你觉得做的好，可以给我买一瓶冰阔落</div>
        <div>
          <img src="@/assets/kele.jpg" width="200" height="100" alt="kele">
        </div>
      </div>
    </NCard>
  </NModal>
</template>
