<template>
    <v-switch hide-details label="Split USB Detect" v-model="usbdetect"/>
    <v-switch hide-details label="Split Watchdog" v-model="watchdog"/>
</template>

<script lang="ts" setup>
import { useKeymapState } from '@/composables/useKeymapState'
import { dottyComputed } from '@/dottyComputed';

const { keymap } = useKeymapState()

const usbdetect = dottyComputed(keymap, 'config.split.usb_detect.enabled');
const watchdog = dottyComputed(keymap, 'config.split.transport.watchdog');
</script>

