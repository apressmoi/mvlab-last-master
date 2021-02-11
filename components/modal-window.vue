<template>
    <div v-if="show" class="modal-shadow" @click.self="closeModal">
        <div class="modal">
            <!-- <div class="modal-close" @click="closeModal">&#10006;</div> -->
            <slot name="title">
                <h3 class="modal-title">Внимание!</h3>
            </slot>
            <slot name="body">
                <div class="modal-content">
                    Потеряна связь с сервером
                </div>
            </slot>
            <slot name="footer">
                <div class="modal-footer">
                    <button class="modal-footer__button" @click="closeModal">
                        Ок
                    </button>
                </div>
            </slot>
        </div>
    </div>
</template>
 
<script>
    export default {
        name: "ModalWindow",
        data: function () {
            return {
                show: false
            }
        },
        methods: {
            closeModal: function () {
                this.show = false
            }
        }
    }
</script>
 
<style scoped
       lang="scss">
    .modal-shadow {
        position: absolute;
        top: 0;
        left: 0;
        min-height: 100%;
        width: 100%;
        background: rgba(0, 0, 0, 0.5);
        z-index:1000;
    }
 
    .modal {
        background: #fff;
        border-radius: 8px;
        padding: 15px;
        min-width: 420px;
        max-width: 480px;
        position: absolute;
        top: 45%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index:1002;
 
        &-close {
            border-radius: 50%;
            color: #fff;
            background: #EDBE45;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            top: 7px;
            right: 7px;
            width: 30px;
            height: 30px;
            cursor: pointer;
            z-index:1002;
        }
 
        &-title {
            color: #EDBE45;
            z-index:1002;
            text-align: center;
            border-bottom: #EDBE45 solid 2px;
            padding: 5px;

        }
 
        &-content {
            margin: 30px 0;
            z-index:1002;
            text-align: center;
        }
 
        &-footer {
            text-align: center;
            &__button {
                background-color: #EDBE45;
                color: #fff;
                border: none;
                text-align: center;
                padding: 8px;
                font-size: 17px;
                font-weight: 500;
                border-radius: 8px;
                min-width: 150px;
                z-index:1002;
            }
        }
    }
</style>