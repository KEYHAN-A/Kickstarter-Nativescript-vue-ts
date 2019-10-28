<template>
    <Label :text="msg" textWrap="true" />
    
</template>

<script lang="ts">
import {Vue, Component, Prop} from 'vue-property-decorator';

@Component({
    components: {

    }
})
export default class ClassComponent extends Vue {
    @Prop()
    private msg: string;
    private name: string;
}
</script>