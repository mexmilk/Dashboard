<template>
    <div class="flexed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block">
        <div class="fixed inset-0 z-10 overflow-y-auto">
            <div class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4">
                <TransitionChild
                as="template"
                enter="ease-out duration-300"
                enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                enter-to="opacity-100 translate-y-0 md:scale-100"
                leave="ease-in duration-200"
                leave-from="opacity-100 translate-y-0 md:scale-100"
                leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                <DialogPanel class="flex w-full transform "></DialogPanel>
            </TransitionChild>
            </div>
        </div>
    </div>
</template>