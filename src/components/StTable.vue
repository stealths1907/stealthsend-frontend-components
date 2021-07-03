<template>
  <div>
    <table class="table">
      <thead v-if="hasHeader">
        <tr>
          <th
            v-for="{ key, title, isSortable, customHeaderClass } in columns"
            :key="key"
            :class="[customHeaderClass]"
          >
            {{ title }}
            <button v-if="isSortable" @click="handleSort(key)">SORT</button>
          </th>
        </tr>
      </thead>
      <tbody name="scale">
        <template v-if="data && data.length > 0">
          <tr
            v-for="(item, index) in data"
            :key="item[identifier] ? item[identifier] : index"
            class="table__row"
            :class="{
              'table__row--is-cancelled':
                item['status'] && item['status'] === 'cancelled'
            }"
            @click="handleRowClick(item)"
          >
            <td
              v-for="{ key, customCellClass } in columns"
              :key="key"
              :class="[customCellClass]"
            >
              <slot :name="key" :item="item" :colkey="key">
                {{ item[key] }}
              </slot>
            </td>
          </tr>
        </template>
        <template v-else>
          <tr key="no-data">
            No data...
          </tr>
        </template>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'StTable',
  props: {
    identifier: {
      type: String,
      required: false,
      default: ''
    },
    columns: {
      type: Array,
      required: true
    },
    data: {
      type: Array,
      required: true
    },
    hasHeader: {
      type: Boolean,
      required: false,
      default: () => {
        return true
      }
    }
  },
  emits: ['sortChanged', 'rowClick'],
  methods: {
    handleSort(col) {
      this.$emit('sortChanged', col)
    },
    handleRowClick(row) {
      this.$emit('rowClick', row)
    }
  }
}
</script>

<style scoped>
.table {
  width: 100%;
  border-spacing: 0 12px;
  font-family: var(--secondary-font);
  /* custom classes for th and td cells */
}
.table td {
  padding: 18px 6px;
  vertical-align: middle;
}
.table thead {
  border-bottom: 1px solid var(--grey100);
  width: 100%;
}
.table thead th {
  text-align: left;
  color: var(--grey1000);
  font-size: 12px;
  letter-spacing: 0.12px;
  line-height: 24px;
  padding: 18px 6px;
}
.table thead tr th:nth-last-child(-n + 2),
.table tbody tr td:nth-last-child(-n + 2) {
  text-align: right !important;
}
.table .table__row {
  box-shadow: none;
  border-left: 4px solid transparent;
  transition: 0.22s;
}

.table .table__row td {
  border-bottom: 1px solid var(--grey100);
  font-size: 12px;
  line-height: 24px;
  letter-spacing: 0.12px;
  color: var(--gray1000);
}

.table .table__row:hover {
  background-color: var(--background50);
}
.table .table__row:last-child {
  border-bottom: 1px solid var(--grey100);
}
.table .cell-center {
  text-align: center !important;
}
.table .cell-right {
  text-align: right !important;
}
</style>
