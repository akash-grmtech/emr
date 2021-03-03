<template>
  <div v-if="rowIdForEdit > 0">
    <prosEdit :_rowIdForEdit="rowIdForEdit" :key="rowIdForEdit" />
  </div>
  <div v-else>
    <prosAdd />
  </div>
</template>

<script>
import prosTbl from '@/components/patient-data/psych-review-of-system/db/client-side/structure/psych-review-of-system-of-a-patient-table'
import prosEdit from '@/components/patient-data/psych-review-of-system/change-layer/pros-edit-design-1'
import prosAdd from '@/components/patient-data/psych-review-of-system/change-layer/add-pros.vue'

export default {
  data: function () {
    return {
      rowIdForEdit: null,
    }
  },
  components: {
    prosEdit,
    prosAdd,
  },
  mounted() {
    const status = prosTbl.isThereSavedPresentDataInTable()
    if (status) {
      this.rowIdForEdit = status[status.length - 1]['clientSideUniqRowId']
    }
  },
}
</script>
